<template>
  <div id="map" class="map">
    <div class="button-bar">
      <button v-on:click="addMapLayer()">terrain</button>
    </div>
  </div>
</template>

<script>
export default {
  mounted () {
    this.createMap()
  },
  computed: {
    location () {
      console.log(this.$store.state.location)
    }
  },
  methods: {
    createMap: () => {
      const mapboxgl = require('mapbox-gl/dist/mapbox-gl.js')
      const accessToken = 'pk.eyJ1Ijoic2hhbmVjYXZhbGllcmUiLCJhIjoib0VGcnZCOCJ9.RY2Dhob09djoIsObhsJMvA'
      mapboxgl.accessToken = accessToken

      this.map = new mapboxgl.Map({
        container: 'map',
        style: 'mapbox://styles/mapbox/light-v9',
        center: [139.692101, 35.689634],
        zoom: 12.5,
        pitch: 0,
        minZoom: 2,
        maxZoom: 20,
        attributionControl: false
      })
    }
  }
}
</script>

<style src="mapbox-gl/dist/mapbox-gl.css"></style>

<style>
.map {
  height: 100vh;
  width: 100vw;
}
.mapboxgl-canvas {
  left: 0;
}
</style>
