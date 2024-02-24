<script>
    import L from 'leaflet';
    import { onMount } from 'svelte';
    let map;

    onMount(() => {
        // Initialize Leaflet map
        map = L.map('map').setView([51.505, 8.09], 19);

        // Add tile layer (optional)
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '© OpenStreetMap contributors'
        }).addTo(map);
    })

</script>

<svelte:head>
	<title>Sverdle</title>
	<meta name="description" content="A Wordle clone written in SvelteKit" />
</svelte:head>

<div id="map"></div>

<style>

</style>
