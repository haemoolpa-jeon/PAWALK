<template>
  <v-app style="padding:5%;">
    <v-container lg4 fluid style="text-align:center;" class="text-xs-center">
      <v-flex md4 class="mx-auto">
        <h1 style="font-size:calc(40px)">Sign In</h1>
        <v-form class="mx-auto; text-xs-center; py-12">
          <v-text-field
            v-model="form.email"
            label="Email"
            single-line
            outlined
            background-color="white"
          ></v-text-field>
          <v-text-field
            v-model="form.password"
            v-on:keyup.enter="signIn"
            label="Password"
            type="password"
            single-line
            outlined
            background-color="white"
          ></v-text-field>
          <v-btn
            @click="signIn"
            color="#E94057"
            style="width:100%; font-size:calc(24px); color:white; min-height:50px;"
          >
            Sign In
          </v-btn>
        </v-form>
        <v-spacer></v-spacer>
      </v-flex>
      <v-flex class="py-12">
        <nuxt-link to="/register" style="text-decoration:none; font-size:20px;"
          ><v-btn text>Register</v-btn></nuxt-link
        >
        <nuxt-link to="/" style="text-decoration:none; font-size:20px;"
          ><v-btn text>Find Password</v-btn></nuxt-link
        >
      </v-flex>
      <nuxt-link to="/aboutus" style="text-decoration:none; font-size:20px;"
          ><v-btn text>About Us</v-btn></nuxt-link
        >
    </v-container>
  </v-app>
</template>
<script>
export default {
  data() {
    return {
      form: {
        email: '',
        password: ''
      }
    }
  },
  async mounted() {},
  methods: {
    async signIn() {
      this.$router.push('/')
      alert('Successfully logged In')
      console.log(r)
    }
  }
}
</script>
<style>
.v-app {
  font-family: 'Noto Sans KR', sans-serif;
}
</style>
