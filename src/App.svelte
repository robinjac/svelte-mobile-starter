<script lang="ts">
	import { Plugins } from '@capacitor/core';
  
	let loc;
	async function getCurrentPosition(){
	  const { Geolocation } = Plugins;
	  const res = await Geolocation.getCurrentPosition()
	  loc = res
	}

  </script>
  
  <div>
	<h1>Geolocation</h1>
	<p>Your location is:</p>
	<p>Latitude: {loc?.coords.latitude}</p>
	<p>Longitude: {loc?.coords.longitude}</p>
  
	<button on:click={getCurrentPosition}>
	  Get Current Location
	</button>
  </div>