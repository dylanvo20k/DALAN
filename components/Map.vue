<template>
  <div id="map"></div>
</template>

<script>

import mapboxgl from 'mapbox-gl';

export default {
  async mounted() {
    let response = {};
    let realLat = this.coordinates[1];
    let realLon = this.coordinates[0];



    let lat = Math.floor(realLat) + 0.5;
    let lon = Math.floor(realLon) + 0.5;


    let coords = [];
    const features = [];

    for (let i = -2; i < 2; i++) {
      for (let j = -2; j < 2; j++) {
        coords.push({
          lat: (lat + i),
          lon: (lon + j)
        })
      }
    }

    try {
      const promises = coords.map(async (coord) => {
        const response = await this.$axios.get(`http://api.openweathermap.org/data/2.5/air_pollution?lat=${coord.lat}&lon=${coord.lon}&appid=ead5ba35ddf4e36ace4c31788680fb61`);
        const aqi = response.data.list[0].main.aqi;
        return {
          "type": "Feature",
          "geometry": {
            "type": "Polygon",
            "coordinates": [
              [
                [coord.lon - 0.5, coord.lat - 0.5],
                [coord.lon + 0.5, coord.lat - 0.5],
                [coord.lon + 0.5, coord.lat + 0.5],
                [coord.lon - 0.5, coord.lat + 0.5],
                [coord.lon - 0.5, coord.lat - 0.5]
              ]
            ]
          },
          "properties": {
            'aqi': aqi,
          }
        };
      });

      const featureArray = await Promise.all(promises);

      features.push(...featureArray);
    } catch (error) {
      console.error(error);
      response = undefined;
    }
    if (response) {

      mapboxgl.accessToken = 'pk.eyJ1IjoiamFsZW5wYWlnZSIsImEiOiJjbGxoZ2hyYWYxOXBiM3JxbHZiaWs3cnptIn0.WfyEN9vvHlJpg3euijmy8Q'; // Replace with your Mapbox Access Token

      const map = new mapboxgl.Map({
        container: 'map',
        style: 'mapbox://styles/mapbox/streets-v11', // Replace with your desired map style
        center: [realLon, realLat], // Replace with your desired center coordinates
        zoom: 10,
      });

      const geoJSON = {
        "type": "FeatureCollection",
        "features": features
      };


      // Add a GeoJSON source and layer
      map.on('load', () => {
        map.addSource('geojson-source', {
          type: 'geojson',
          data: geoJSON
        });
        console.log(geoJSON);
        map.addLayer({
          id: 'geojson-layer',
          type: 'fill',
          source: 'geojson-source',
          paint: {
            'fill-color': [
              'match',
              ['get', 'aqi'], // Replace 'yourProperty' with the property you want to base the color on
              1, 'rgb(50, 205, 50)',
              2, 'rgb(50, 205, 25)',
              3, 'rgb(255, 255, 0)',
              4, 'rgb(255, 140, 0)',
              5, 'rgb(255, 0, 0)',
              /* Add more conditions and colors as needed */
              'rgb(0, 0, 0)'// Default color if none of the conditions match
            ],
            'fill-opacity': 0.5, // Adjust opacity as needed
          },
        });
      });
    }
  },
  props: {
    coordinates: {
      type: Array, // Define the type of data expected (in this case, an array for coordinates)
      required: true, // Make the prop required if you want to ensure it's always provided
    }
  }
}
</script>

<style>
#map {
  height: 25rem;
  width: 100%;
}
</style>
