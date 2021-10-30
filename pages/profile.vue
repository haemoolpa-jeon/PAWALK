<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto" id="profileHeaderCard">
        <v-card-title class="justify-left">
          <h3 class="text-lg-center" id="profileTitle" style="font-size: 28px;">User Profile</h3>
        </v-card-title>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-row id="profilePicture" justify="center" align="center">
        <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">
        <v-badge
        id="badgeCam"
        bordered
        bottom
        icon="mdi-camera-plus"
        large
        color="white"
        offset-x="10"
        offset-y="10"
        >
          <v-avatar size="250" tile>
            <img
              src="https://cdn.vuetifyjs.com/images/john.jpg"
              alt="JF"
              id="profileAvatar"
            />
          </v-avatar>
        </v-badge>
        </v-row>
        <v-row id="infoHeading" style="font-family: Arial;font-size: 12pt;">
        <v-col style="flex-grow: 0; padding-left: 30px">
            <v-icon
                small
                color="black"
            >
            info
            </v-icon>
        </v-col>
        <v-col style="flex-grow: 1;"> 
            <h3 style="font-family: Arial;font-size: 12pt;">Personal Information</h3>
        </v-col>
        <v-col style="flex-grow: 0; padding-right: 50px;">
            <v-btn
              fab
              icon
              small
            >
              <v-icon color="green">
                edit
              </v-icon>
            </v-btn>
        </v-col>
        </v-row>
        <v-list one-line style="font-family: Arial;font-size: 14pt;">
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Name</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >John Smith</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Email</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >jsmith123@gmail.com</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Phone</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >(+61) 412 345 678</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Gender</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse">Male</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField"
                >Date of Birth</v-list-item-title
              >
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >15/06/1996</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField"
                >Area</v-list-item-title
              >
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >Gold Coast CBD</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-row id="infoHeading" style="font-family: Arial;font-size: 12pt;">
        <v-col style="flex-grow: 0; padding-left: 30px">
            <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">
            <v-icon
                small
                color="black"
            >
            mdi-dog
            </v-icon>
        </v-col>
        <v-col style="flex-grow: 1;"> 
            <h3 style="font-family: Arial;font-size: 12pt;">Owned Dogs</h3>
        </v-col>
        <v-col style="flex-grow: 0; padding-right: 50px;">
            <v-btn
              fab
              icon
              small
            >
              <v-icon color="green">
                edit
              </v-icon>
            </v-btn>
        </v-col>
        </v-row>
        <v-row id="interestButtons">
          <v-btn
            style="margin-left: 30px"
            id="interest"
            rounded
            color="gray"
            outlined
          >
            Yorkshier Terrier
          </v-btn>
          <v-btn id="interest" rounded color="gray" outlined> Poodle </v-btn>
        </v-row>
        <v-row id="infoHeading" style="font-family: Arial;font-size: 12pt;">
        <v-col style="flex-grow: 0; padding-left: 30px">
            <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">
            <v-icon
                small
                color="black"
            >
            mdi-map
            </v-icon>
        </v-col>
        <v-col style="flex-grow: 1;"> 
            <h3 style="font-family: Arial;font-size: 12pt;">Favourite Parks</h3>
        </v-col>
        <v-col style="flex-grow: 0; padding-right: 50px;">
            <v-btn
              fab
              icon
              small
            >
              <v-icon color="green">
                edit
              </v-icon>
            </v-btn>
        </v-col>
        </v-row>
        <v-list one-line style="font-family: Arial;font-size: 14pt;">
          <v-list-item style="padding-top: 10px;">
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Palm Beach Offleash</v-list-item-title>
              <v-list-item-title id="infoField">Musgrave Park Agility</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <div id="bottom">
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>

<style scoped>
#profileHeaderCard {
  background-color: green;
}
#profileTitle {
  color: white;
}
#profilePicture {
  padding: 5%;
}
#profileAvatar {
  border-radius: 10%;
}
#leftListItem {
  padding-left: 30px;
}
#rightListItem {
  padding-right: 30px;
}
#infoHeading {
  padding-top: 20px;
  font-size: 75%;
}
#infoField {
  color: #8d8d8d;
}
#infoResponse {
  color: #8d8d8d;
  font-weight: bold;
}
#interestButtons {
  padding-top: 10px;
}
#interest {
  margin: 10px 10px;
}
#bottom {
    padding-bottom: 50px;
}
</style>