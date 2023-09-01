<script lang="ts">
  import { environment } from './environments/environment';
  import Map from './lib/Map.svelte';
	export let ready: boolean;
</script>

<svelte:head>
	<script defer async
	src="https://maps.googleapis.com/maps/api/js?key={environment.googleMapsApiKey}&callback=initMap">
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
