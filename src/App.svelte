<script lang="ts">
	import type { GeolocationPosition } from '@capacitor/core'; 
	import { Geolocation } from '@capacitor/core';
	
	let loc: GeolocationPosition;
	
	async function getCurrentPosition(): Promise<void> {
		loc = await Geolocation.getCurrentPosition();
	}

</script>
  
<div>
	<h1>Geolocation</h1>
	<p>Your location is:</p>
	<p>Latitude: {loc?.coords.latitude ?? ""}</p>
	<p>Longitude: {loc?.coords.longitude ?? ""}</p>

	<button on:click={getCurrentPosition}>
		Get Current Location
	</button>
</div>

<style type="text/scss">
	$borderColor: red;

	button {
		border: 1px solid $borderColor;
		border-radius: 5px;
		background-color: purple;
		color: white;
		cursor: pointer;

		&:active {
			background-color: rgb(190, 0, 190);
		}
	}

</style>