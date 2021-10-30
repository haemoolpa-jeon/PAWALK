<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        <img src="~/assets/logo.png" />
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-center">
          <h3 class="text-lg-center">Welcome to PAWALK</h3>
        </v-card-title>
        <v-card-text class="justify-center">
          <p class="text-md-center">Find places to walk and play with your dogs!</p>
        </v-card-text>
        <v-hover v-slot="{ hover }">
          <v-img justify="center" max-height="100%" max-width="100%" contain>
            <img src="~/assets/1.jpg" />
            <v-expand-transition>
            <div
              v-if="hover"
              class="d-flex transition-fast-in-fast-out light-green darken-2 v-card--reveal text-h2 white--text"
              style="height: 50%;"
            >
              <a style="font-size: 2rem; text-decoration:none; color:white;" href="https://www.cesarsway.com/5-ways-to-make-the-walk-more-interesting">Accessed from https://www.cesarsway.com/5-ways-to-make-the-walk-more-interesting/</a>
            </div>
          </v-expand-transition>
          </v-img>
        </v-hover>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-center">
          <h3 class="text-lg-center">VIEW TOP DOG PARKS</h3>
        </v-card-title>
        <v-card-text class="justify-center">
          <p class="text-md-center">VIEW THE REVIEWS OF DOG PARKS</p>
        </v-card-text>
         <v-sheet
            class="mx-auto d-none d-md-block"
            elevation="0"
            max-width="1200"
            style="background-color:#F8F8F8"
          >
            <v-slide-group
              v-model="model"
              class="pa-4"
              center-active
              show-arrows
            >
              <v-slide-item
                v-for="(item, i) in items"
                :key="i"
                v-slot:default="{ toggle }"
                disabled
              >
                <v-card @click="toggle" class="ma-4" height="300" width="500">
                  <v-card-title class="mb-n8">{{ item.title }}</v-card-title>
                  <v-card-actions class="my-n5 ml-1">
                    <v-rating v-model="item.rating" readonly dense></v-rating>
                    <span class="mr-2 caption"> {{ item.rating }}Stars </span>
                  </v-card-actions>
                  <v-card-text>
                    <p>
                      {{ item.text }}
                    </p>
                  </v-card-text>
                </v-card>
              </v-slide-item>
            </v-slide-group>
          </v-sheet>
        <v-card-actions class="justify-center">
              <v-btn
                elevation="2"
                x-large
                color="warning"
                nuxt
                class="text-center"
                to="/ranking"
              >
                VIEW MORE REVIEWS
              </v-btn>
            </v-card-actions>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-center">
          <h3 class="text-lg-center">SELECT BETWEEN TWO OPTIONS</h3>
        </v-card-title>
        <v-card-text class="justify-center">
          <p class="text-md-center">Find places to walk and play with your dogs!</p>
        </v-card-text>
          <v-card
            class="pa-md-3 mx-auto my-4"
            max-width="550"
            outlined
            :style="'border: 1px solid blue;'"
          >
            <v-list-item three-line>
              <v-list-item-content>
                <v-list-item-title class="text-h5 mb-1">
                  <NuxtLink to="/findNearby"> DOG PARK NEARBY</NuxtLink>
                </v-list-item-title>
                <v-list-item-subtitle>Find great places near you</v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              >
                <v-hover v-slot="{ hover }">
                  <v-img>
                    <img src="~/assets/2.png">
                    <v-expand-transition>
                      <div
                        v-if="hover"
                        class="d-flex transition-fast-in-fast-out light-green darken-2 v-card--reveal text-h2 white--text"
                        style="height: 50%;"
                      >
                        <p style="font-size: .5rem; text-decoration:none; color:white;">Captured from map</p>
                      </div>
                    </v-expand-transition>
                  </v-img>
                </v-hover>
              </v-list-item-avatar>
            </v-list-item>

            <v-card-actions>
              <v-btn
                outlined
                rounded
                text
                color="primary"
                nuxt
                to="/findNearby"
              >
                FIND
              </v-btn>
            </v-card-actions>
          </v-card>
          <v-card
            class="pa-md-3 mx-auto my-4"
            max-width="550"
            outlined
            :style="'border: 1px solid red;'"
          >
            <v-list-item three-line>
              <v-list-item-content>
                <v-list-item-title class="text-h5 mb-1">
                  <NuxtLink to="/avoid">AVOID DOGS</NuxtLink>
                </v-list-item-title>
                <v-list-item-subtitle>Find safe routes from dogs</v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              >
              <v-hover v-slot="{ hover }">
                <v-img>
                  <img src="~/assets/3.png">
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="d-flex transition-fast-in-fast-out light-green darken-2 v-card--reveal text-h2 white--text"
                      style="height: 50%;"
                    >
                      <p style="font-size: .5rem; text-decoration:none; color:white;">Captured from map</p>
                    </div>
                  </v-expand-transition>
                </v-img>
              </v-hover>
              </v-list-item-avatar>
            </v-list-item>

            <v-card-actions>
              <v-btn
                outlined
                rounded
                text
                color="red"
                nuxt
                to="/avoid"
              >
                FIND
              </v-btn>
            </v-card-actions>
          </v-card>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      center: {lat:-28.016666, lng: 153.399994},
      zoom: 15,
      currentLocation: {lat:-28.016666, lng: 153.399994},
      items: [
      {
        title: "Gold Coast Regional Botanic Garden",
        rating: "4.9",
        text: "Benowa QLD 4217"
      },
      {
        title: "Scenic Dog Park",
        rating: "4.8",
        text: "Corner of Scenic Avenue and Bamboo Avenue"
      },
      {
        title: "Sun Valley Park",
        rating: "4.6",
        text: "9 Sun Valley Dr Ashmore QLD 4214"
      }
      ]
    }
  }
}


</script>


<style>

.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: .7;
  position: absolute;
  width: 100%;
}

</style>
