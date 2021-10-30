<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-card
        tile
        color="#333333"
        width="100%"
        style="padding: 15px 10px; align-items:flex-end; position:absolute; bottom:0px;"
      >
        <div style="text-align:center">
          <div
            v-if="loggedIn"
            @click="logout"
            style="color:white; font-size:1.5rem; text-decoration:none;"
            class="logout-link"
          >
            Log Out
          </div>
          <nuxt-link
            v-else
            to="/login"
            style="color:white; font-size:1.5rem; text-decoration:none;"
            ><div>Log In</div></nuxt-link
          >
        </div>
      </v-card>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-spacer></v-spacer>
      <!--login icon-->
      <div class="my-2 text-center">
        <v-btn
          v-if="!loggedIn"
          color="green"
          nuxt
          to="/login"
          raised
          class="white--text font-weight-bold subtitle-1"
          >Sign In</v-btn
        >
        <nuxt-link
          v-if="loggedIn"
          to="/profile"
          style="color:green; text-decoration:none;"
          class="subtitle-2"
          >My Profile</nuxt-link
        >
      </div>
      <div class="mt-2 text-center">
        <v-btn
          v-if="!loggedIn"
          color="green"
          nuxt
          to="/register"
          text
          raised
          class="font-weight-bold title d-none d-lg-block"
          >Register</v-btn
        >
      </div>
      <v-spacer></v-spacer>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}Team Beaver</span>
      <v-divider></v-divider>
      <span>Created by Nuxt.js using Vue.js and Vuetify as frontend Framework</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      loggedIn: true,
      items: [
        {
          icon: 'mdi-apps',
          title: 'HOME',
          to: '/'
        },
        {
          icon: 'mdi-map',
          title: 'DOG PARK MAP',
          to: '/findNearby'
        },
        {
          icon: 'mdi-format-list-bulleted-square',
          title: 'REVIEWS AND RATINGS',
          to: '/ranking'
        },
        {
          icon: 'mdi-information',
          title: 'ABOUT US',
          to: '/aboutus'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'PAWALK'
    }
  },
  methods: {
    logout() {
      this.loggedIn = false
      alert('Successfully logged out')
      this.$router.push('/')
    }
  }
}
</script>
