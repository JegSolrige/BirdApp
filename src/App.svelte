<script lang="ts">
  import { environment } from './environments/environment';
  import Map from './lib/Map.svelte';
	export let ready: boolean;

  console.log(environment.apiKey);
</script>

<svelte:head>
	<script defer async
	src="https://maps.googleapis.com/maps/api/js?key={environment.apiKey}&callback=initMap">
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
