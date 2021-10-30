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
        <v-img justify="center">
          <img src="~/assets/1.jpg" />
        </v-img>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-center">
          <h3 class="text-lg-center">VIEW TOP DOG PARKS</h3>
        </v-card-title>
        <v-card-text class="justify-center">
          <p class="text-md-center">VIEW THE RANKING OF DOG PARKS</p>
        </v-card-text>
        <v-card-actions class="justify-center">
              <v-btn
                elevation="2"
                x-large
                color="warning"
                nuxt
                class="text-center"
                to="/ranking"
              >
                VIEW RANKING
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
              ></v-list-item-avatar>
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
                <v-list-item-title class="text-h5 mb-1" to="/avoid">
                  AVOID DOG ATTACKS
                </v-list-item-title>
                <v-list-item-subtitle>Find safe places from dogs</v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
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
