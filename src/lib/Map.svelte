<script lang="ts">
    //import mapStyles from './map-styles'; // optional

    let map: google.maps.Map;
    let container: HTMLElement;
    let zoom = 8;
    let center = {lat: -34.397, lng: 150.644};
    let marker: google.maps.Marker | undefined = undefined;
   
    import { onMount } from 'svelte';

    onMount(async () => {
        map = new google.maps.Map(container, {
            zoom,
            center,
            //styles: mapStyles // optional
        });

        google.maps.event.addListener(map, "click", (event) => {
            addMarker(event.latLng, map);
        });
    });

    // Adds a marker to the map.
    function addMarker(location: google.maps.LatLng, map: google.maps.Map) {
    if (marker !== undefined) {
        marker.setMap(null);
    }
    // Add the marker at the clicked location, and add the next-available label
    // from the array of alphabetical characters.
    marker = new google.maps.Marker({
        position: location,
        map: map,
    });
    }
</script>

<style>
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.full-screen-bordered {
  width: 75%;
  height: 75%;
}
</style>
<div class="container">
    <div class="full-screen-bordered" bind:this={container}></div>
</div>
