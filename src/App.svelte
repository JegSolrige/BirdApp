<script lang="ts">
  import Map from './lib/Map.svelte';
	export let ready: boolean;
  
  let googleMapsApiKey = import.meta.env.VITE_GOOGLE_MAPS_API_KEY;
</script>

<svelte:head>
	<script defer async
	src="https://maps.googleapis.com/maps/api/js?key={googleMapsApiKey}&callback=initMap">
	</script>
</svelte:head>

<style>
  :global(body) {
    padding: 0;
  }
  </style>
  
  { #if ready }
  <Map></Map>
  { /if }
