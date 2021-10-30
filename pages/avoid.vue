<template>
  <div>
    <v-card class="logo py-4 d-flex justify-center">
      <h1>DOG PARK MAP</h1>
    </v-card>
    <GMap ref="gMap" :zoom="zoom" :center="center" language="en" :options="{fullscreenControl: false}">
      <GMapMarker
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
      <GMapCircle :options="circleOptions"/>
    </GMap>
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="red lighten-2"
          dark
          v-bind="attrs"
          v-on="on"
          class="my-4 py-4"
        >
          OPTIONS
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          SELECT OPTIONS
        </v-card-title>

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

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            APPLY
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="BLACK lighten-2"
          dark
          v-bind="attrs"
          v-on="on"
          class="my-4 py-4"
        >
          FILTERS
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          SELECT OPTIONS
        </v-card-title>

        <v-container fluid>
          <v-checkbox
            v-model="checkbox1"
            :label="`Suitable for social activities`"
          ></v-checkbox>
          <v-checkbox
            v-model="checkbox2"
            :label="`Suitable for running`"
          ></v-checkbox>
          <v-checkbox
            v-model="checkbox2"
            :label="`Quiet Area`"
          ></v-checkbox>
          <v-checkbox
            v-model="checkbox2"
            :label="`Nature Friendly`"
          ></v-checkbox>
        </v-container>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            APPLY
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name:'Map',
  data() {
    return {
      center: {lat:-28.016666, lng: 153.399994},
      zoom: 15,
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
    clusterStyle: [
      {
        url: "https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/m1.png",
        width: 56,
        height: 56,
        textColor: "#fff"
      }
    ]
    }
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