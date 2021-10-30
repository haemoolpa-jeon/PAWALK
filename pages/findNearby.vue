<template>
  <div>
    <v-card class="logo py-4 d-flex justify-center">
      <h1>DOG PARK MAP</h1>
    </v-card>
    <GMap ref="gMap" :zoom="zoom" :center="center" language="en" :options="{fullscreenControl: false}">
        <GMapMarker
          :v-if="checkbox1=false"
          v-for="location in locations"
          :key="location.id"
          :position="{lat: location.lat, lng: location.lng}"
          @click="currentLocation = location"
        >
          <GMapInfoWindow :options="{maxWidth: 300}">
            <code>
              {{ location.name }}
            </code>
          </GMapInfoWindow>
        </GMapMarker>
        <GMapMarker
          :v-if="checkbox2=false"
          v-for="location in locations2"
          :key="location.id"
          :position="{lat: location.lat, lng: location.lng}"
          @click="currentLocation = location"
        >
          <GMapInfoWindow :options="{maxWidth: 300}">
            <code>
              {{ location.name }}
            </code>
          </GMapInfoWindow>
        </GMapMarker>
      <GMapCircle :options="circleOptions"/>
      <GMapCircle :options="circleOptions1"/>
      <GMapCircle :options="circleOptions2"/>
      <GMapCircle :options="circleOptions3"/>
      <GMapCircle :options="circleOptions4"/>
      <GMapCircle :options="circleOptions5"/>
    </GMap>
      
        <v-container fluid>
          <v-checkbox
            v-model="checkbox1"
            :label="`OFF-LEASH`"
          ></v-checkbox>
          <v-checkbox
            v-model="checkbox2"
            :label="`LEASH`"
          ></v-checkbox>
        </v-container>
  </div>
</template>

<script>
export default {
  name:'Map',
  data() {
    return {
      center: {lat:-28.016666, lng: 153.399994},
      zoom: 15,
      address: "",
      currentLocation: {lat:-28.016666, lng: 153.399994},
      locations: [
        {
          name: "Scenic Dog Park",
          lat: -27.99569,
          lng: 153.39767
        },
        {
          name: "Cabana Offleash Dog Area",
          lat: -28.00672,
          lng: "153.37868"
        },
        {
          name: "Robina Parkway Fenced Agility Dog Park",
          lat: "-28.03937",
          lng: "153.38993"
        }
      ],
      locations2: [
        {
          name: "Laguna Park",
          lat: -28.1264453,
          lng: 153.4684613
        },
        {
          name: "South Stradbroke",
          lat: -27.8352622,
          lng: 153.3579485
        },
        {
          name: "Keith Hunt Park",
          lat: -27.9544452,
          lng: 153.3906413
        }
      ],
    circleOptions: {
      strokeColor: '#0000FF',
      strokeOpacity: 0.8,
      strokeWeight: 2,
      fillColor: '#0000FF',
      fillOpacity: 0.35,
      center: {lat: -27.99569, lng: 153.39767},
      radius: 300 //
    },
    circleOptions1: {
      strokeColor: '#0000FF',
      strokeOpacity: 0.8,
      strokeWeight: 2,
      fillColor: '#0000FF',
      fillOpacity: 0.35,
      center: {lat: -28.00672, lng: 153.37868},
      radius: 300 //
    },
    circleOptions2: {
      strokeColor: '#0000FF',
      strokeOpacity: 0.8,
      strokeWeight: 2,
      fillColor: '#0000FF',
      fillOpacity: 0.35,
      center: {lat: -28.03937,
          lng: 153.38993},
      radius: 300 //
    },
    circleOptions3: {
      strokeColor: '#FF0000',
      strokeOpacity: 0.8,
      strokeWeight: 2,
      fillColor: '#FF0000',
      fillOpacity: 0.35,
      center: {lat: -28.1264453, lng: 153.4684613},
      radius: 300 //
    },
    circleOptions4: {
      strokeColor: '#FF0000',
      strokeOpacity: 0.8,
      strokeWeight: 2,
      fillColor: '#FF0000',
      fillOpacity: 0.35,
      center: {lat: -27.8352622,
          lng: 153.3579485},
      radius: 300 //
    },
    circleOptions5: {
      strokeColor: '#FF0000',
      strokeOpacity: 0.8,
      strokeWeight: 2,
      fillColor: '#FF0000',
      fillOpacity: 0.35,
      center: {lat: -27.9544452,
          lng: 153.3906413},
      radius: 300 //
    },
    
    clusterStyle: [
      {
        url: "https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/m1.png",
        width: 56,
        height: 56,
        textColor: "#fff"
      }
    ]
    }
  },
  methods: {
       locatorButtonPressed() {
         navigator.geolocation.getCurrentPosition(
          position => {
            console.log(position.coords.latitude);
            console.log(position.coords.longitude);
          },
          error => {
            console.log(error.message);
          },
        )
       },
     }
}
</script>

<style lang="scss">
  .gmap-holder {
    position:relative;
    height: 100vh;
  }
  .gmap-wrapper {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    width: 100%;
    height: 100%;
    min-height: 500px;
  }
</style>