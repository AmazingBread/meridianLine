<template>
	<div id="map"></div>
</template>

<script>
import L from "leaflet";
import "leaflet/dist/leaflet.css";

export default {
	name: "HelloWorld",
	props: {
		msg: String,
	},
	data() {},
	mounted() {
		this.init();
	},
	methods: {
		init() {
			let map = new L.map("map").setView([51.505, -0.09], 13);
			L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
				maxZoom: 19,
				attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
			}).addTo(map);
		},
	},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
body {margin:0;}
html {
    margin:0;
    /* min-width: 320px; */
}
#map {
	height: 100vh;
	z-index: 99;
}
</style>
