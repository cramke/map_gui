<script>
	/*
	This is an example of using Svelte features with Leaflet. Original blog post here: https://imfeld.dev/writing/leaflet_with_svelte
	
	The toolbar and the marker popups are both implemented by embedding Svelte components inside Leaflet elements. The marker and lines are toggled by updating the map from reactive statements.
	
	Any questions? Ask me at dimfeld on Twitter!
	
	Thanks to heroicons.dev for all the icons used here.
	*/
	
	import L from 'leaflet';
	import MapToolbar from './MapToolbar.svelte';
	let map;
	
	const markerLocations = [
		[51, 9],
		[50, 8]
	];
	
	const initialView = [51, 9];
	function createMap(container) {
		let m = L.map(container, {preferCanvas: true }).setView(initialView, 10);
		L.tileLayer(
			'https://{s}.basemaps.cartocdn.com/rastertiles/voyager/{z}/{x}/{y}{r}.png',
			{
			attribution: `&copy;<a href="https://www.openstreetmap.org/copyright" target="_blank">OpenStreetMap</a>,
				&copy;<a href="https://carto.com/attributions" target="_blank">CARTO</a>`,
			subdomains: 'abcd',
			maxZoom: 14,
			}
		).addTo(m);

		return m;
  	}
	
	let eye = true;
	let lines = true;
	
	let toolbar = L.control({ position: 'topright' });
	let toolbarComponent;
	toolbar.onAdd = (map) => {
		let div = L.DomUtil.create('div');
		toolbarComponent = new MapToolbar({
			target: div,
			props: {}
		});

		toolbarComponent.$on('click-eye', ({ detail }) => eye = detail);
		toolbarComponent.$on('click-lines', ({ detail }) => lines = detail);
		toolbarComponent.$on('click-reset', () => {
			map.setView(initialView, 5, { animate: true })
		});
		toolbarComponent.$on('add-waypoint', ({ detail }) => {
			if(detail) {
				map.on('click', onMapClick);
			} else {
				map.off('click', onMapClick);
			}
		});

		return div;
	}

	toolbar.onRemove = () => {
		if(toolbarComponent) {
			toolbarComponent.$destroy();
			toolbarComponent = null;
		}
	};
	
	function createLines() {
		return L.polyline(markerLocations, { color: '#E4E', opacity: 0.5 });
	}

	function onMapClick(e) {
		const lat = e.latlng.lat;
		const lng = e.latlng.lng;
		markerLocations.push([lat, lng]);
		lineLayers.remove();
		lineLayers = createLines();
		lineLayers.addTo(map);	
	}

	let lineLayers;
	function mapAction(container) {
		map = createMap(container); 
		toolbar.addTo(map);
		
		lineLayers = createLines();
		lineLayers.addTo(map);

		map.on('click', onMapClick);
			
		return {
		destroy: () => {
					toolbar.remove();
					map.remove();
					map = null;
				}
		};
	}
	
	// We could do these in the toolbar's click handler but this is an example
	// of modifying the map with reactive syntax.
	$: if(lineLayers && map) {
		if(lines) {
			lineLayers.addTo(map);
		} else {
			lineLayers.remove();
		}
	}

	function resizeMap() {
		if(map) { map.invalidateSize(); }
  	}

</script>
<svelte:window on:resize={resizeMap} />

<style>
    .map {
        height: 100vh; /* or any other height */
        width: 100%; /* or any other width */
    }
</style>

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.6.0/dist/leaflet.css"
   integrity="sha512-xwE/Az9zrjBIphAcBb3F6JVqxf46+CDLwfLMHloNu6KEQCAWi6HcDUbeOfBIptF7tcCzusKFjFw2yuvEpDL9wQ=="
   crossorigin=""/>
<div>{markerLocations}</div>
<div class="map" use:mapAction />