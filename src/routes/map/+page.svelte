<script>
    import L from 'leaflet';
    import { onMount } from 'svelte';
    let map;

    onMount(() => {
        // Initialize Leaflet map
        map = L.map('map').setView([51.0166949, 13.7393911], 19);

        // Add tile layer (optional)
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '© OpenStreetMap contributors'
        }).addTo(map);

        var lineCoordinates = [
            [51.0166949, 13.7393911],
            [51.0163905, 13.7396704],
            [51.0162959, 13.7398762],
            [51.0162704, 13.7401042],
            [51.016217, 13.7403173]
        ];
        var polyline = L.polyline(lineCoordinates, {color: 'red'}).addTo(map);
    })

</script>

<svelte:head>
	<title>Map</title>
	<meta name="description" content="Displays a map from OSM and adds a vector." />
</svelte:head>

<div id="map"></div>

<style>
    #map {
      height: 100vh; /* or any other height */
      width: 100%; /* or any other width */
    }
</style>