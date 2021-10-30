<template>
  <v-app class="pt-10">
    <h1 style="text-align:center;">Register</h1>
    <v-window v-model="step">
      <v-window-item :value="1">
        <v-container fluid app>
          <v-row app>
            <v-col xs="12" sm="12" md="6" lg="4" xl="4" class="mx-auto" app>
              <h2 style="text-align:center;" class="subtitle-2 pb-2">
                Please fill in the form
              </h2>
              <v-form ref="form" v-model="form1">
                <label>Email</label>
                <v-text-field
                  id="email"
                  v-model="email"
                  :rules="[rules.email]"
                  label="Email"
                  type="email"
                  required
                  filled
                  style="min-height:96px;"
                  outlined
                  background-color="white"
                  class="mt-2"
                ></v-text-field>
                <label>Password</label>
                <v-text-field
                  id="pwd"
                  v-model="pwd"
                  :counter="20"
                  :rules="[rules.pwd, rules.length(8)]"
                  label="Password"
                  type="password"
                  required
                  filled
                  style="min-height:96px;"
                  outlined
                  background-color="white"
                  class="mt-2"
                ></v-text-field>
                <label>Password Check</label>
                <v-text-field
                  id="pwdCheck"
                  v-model="pwdCheck"
                  :counter="20"
                  :rules="[
                    rules.pwd,
                    passwordConfirmationRule,
                    rules.length(8)
                  ]"
                  label="Password Check"
                  type="password"
                  required
                  filled
                  style="min-height:96px;"
                  outlined
                  background-color="white"
                  class="mt-2"
                ></v-text-field>
                <v-spacer></v-spacer>
              </v-form>
            </v-col>
          </v-row>
          <v-row>
            <v-col
              xs="12"
              sm="12"
              md="6"
              lg="4"
              xl="4"
              app
              class="justify-space-between row mx-auto"
            >
              <v-btn
                :disabled="!form1"
                @click="
                  step++
                "
                class="white--text"
                color="#E94057"
                depressed
                style="width:100%"
                x-large
              >
                Next
              </v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-window-item>
      <v-window-item :value="2">
        <v-container fluid app>
          <v-row app>
            <v-col xs="12" sm="12" md="6" lg="4" xl="4" class="mx-auto" app>
              <h2 style="text-align:center;" class="subtitle-2 pb-2">
                Additional Information
              </h2>
              <h3 style="text-align:center;" class="caption pb-2">
                For better service it would be great if you input additional details
              </h3>
              <v-form ref="form" v-model="secondForm">
                <label>Name</label>
                <v-text-field
                  id="name"
                  v-model="form2.name"
                  :counter="8"
                  label="Name"
                  type="string"
                  filled
                  style="min-height:96px;"
                  single-line
                  outlined
                  background-color="white"
                  required
                  class="mt-2"
                ></v-text-field>
                <label>Phone Number</label>
                <v-text-field
                  id="phoneNumber"
                  v-model="form2.phoneNumber"
                  :counter="11"
                  :rules="[rules.length(11)]"
                  label="Phone Number"
                  type="number"
                  filled
                  style="min-height:96px;"
                  single-line
                  outlined
                  background-color="white"
                  required
                  class="mt-2"
                ></v-text-field>
                <label>Birthday</label>
                <v-menu
                  ref="menu"
                  v-model="menu"
                  :close-on-content-click="false"
                  full-width
                  max-width="290"
                >
                  <template v-slot:activator="{ on }">
                    <v-text-field
                      v-model="form2.bdate"
                      v-on="on"
                      label="Please Click to input your birthday"
                      readonly
                      background-color="white"
                      outlined
                      single-line
                      required
                      class="mt-2"
                    ></v-text-field>
                  </template>
                  <v-date-picker
                    ref="picker"
                    v-model="form2.bdate"
                    max="2021-12-31"
                    min="1920-01-01"
                    locale="en-au"
                  ></v-date-picker>
                </v-menu>
                <label>Interested Excercise</label>
                <v-text-field
                  id="InEx"
                  v-model="form2.InEx"
                  :counter="15"
                  label="Your interests"
                  type="text"
                  filled
                  style="min-height:96px;"
                  single-line
                  outlined
                  background-color="white"
                  required
                  class="mt-2"
                ></v-text-field>
                <v-spacer></v-spacer>
                <v-btn
                  :disabled="!secondForm || !form2.bdate || !form2.InEx"
                  @click="
                    step++
                  "
                  class="white--text"
                  color="#E94057"
                  depressed
                  style="width:100%"
                  x-large
                  >Register</v-btn
                >
              </v-form>
            </v-col>
          </v-row>
        </v-container>
      </v-window-item>
      <v-window-item :value="3">
        <v-container fluid app>
          <v-row app>
            <v-col xs="12" sm="12" md="6" lg="4" xl="4" class="mx-auto" app>
              <h2 class="title pb-8">
                Registration Complete
              </h2>

              <v-btn to="/leaderboard" color="white" style="width:100%" x-large
                >Start Using GYMATCH</v-btn
              >
            </v-col>
          </v-row>
        </v-container>
      </v-window-item>
    </v-window>
  </v-app>
</template>
<script>
export default {
  components: {},
  data: () => ({
    agreement1: false,
    agreement2: false,
    diagnosis: undefined,
    email: undefined,
    form1: false,
    secondForm: false,
    form2: {
      name: '',
      phoneNumber: '',
      bdate: '',
      diagnosis: ''
    },
    isLoading: false,
    pwd: undefined,
    pwdCheck: undefined,
    picker: new Date().toISOString().substr(0, 10),
    step: 1,
    date: null,
    menu: false,
    rules: {
      email: (v) => (v || '').match(/@/) || 'Please Check your email address',
      length: (len) => (v) =>
        (v || '').length >= len ||
        `Too short, please enter more than ${len}`,
      pwd: (v) =>
        (v || '').match(/^(?=.*[a-z])(?=.*\d).+$/) ||
        'Password needs to be longer than 8 characters',
      required: (v) => !!v || 'Please check'
    }
  }),
  computed: {
    passwordConfirmationRule() {
      return this.pwd === this.pwdCheck || 'Password does not match'
    }
  },
  watch: {
    menu(val) {
      val && setTimeout(() => (this.$refs.picker.activePicker = 'YEAR'))
    }
  },
  mounted() {}
}
</script>
<style>
.scroll {
  overflow-y: auto;
}
.v-app {
  font-family: 'Noto Sans KR', sans-serif;
}
</style>
