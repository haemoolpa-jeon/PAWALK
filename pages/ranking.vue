<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        <h1>Reviews and Ratings</h1>
      </v-card>
      <v-col
        v-for="card1 in park"
        :key="card1.Park"
        >
        <v-card
        class="elevation-5 my-10 mx-auto"
        width="600"
        >
          <a :href="'https://www.google.com/maps/place/'+ card1.Park">
            <v-card-title class="text-h5" v-text="card1.Park"> 
            </v-card-title>
          </a>
          <v-card-text>
            {{ card1.Suburb }}
            <div class="text-center mt-12">
              <v-rating
                v-model="rating"
                color="yellow darken-3"
                background-color="grey darken-1"
                empty-icon="$ratingFull"
                half-increments
                large
              ></v-rating>
            </div>
          </v-card-text>
        </v-card>
      </v-col>                                        
      
    </v-col>
  </v-row>
</template>


<script>
  export default {
    data () {
      return {
        parks: [
        { id: 1, title: '', src: 'https://picsum.photos/id/190/200/300', job: 'Car Dealer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', link: '/leaderboard', rating: 4, flex: 12 },
        { id: 2, title: 'Julian Dasilvia', src: 'https://picsum.photos/id/400/200/300', job: 'Graphic Designer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', rating: 4, flex: 12 },
        { id: 3, title: 'Mike Lyne', src: 'https://picsum.photos/id/160/200/300', job: 'Officemen', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', rating: 4, flex: 12 },
        { id: 4, title: 'Claire Kumas', src: 'https://picsum.photos/id/150/200/300', job: 'Teacher', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', rating: 4, link: '/leaderboard', flex: 12 },
        { id: 5, title: 'Blair Dota', src: 'https://picsum.photos/id/237/200/300', job: 'Shop Owner', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',  rating: 4,flex: 12 },
        { id: 6, title: 'Connor Ryan', src: 'https://picsum.photos/id/200/200/300', job: 'Software Engineer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',  rating: 4, flex: 12 },
        { id: 7, title: 'Dendi Navidad', src: 'https://picsum.photos/id/300/200/300', job: 'Graphic Designer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', rating: 4, flex: 12 },
        ],
        park: []
      }
    },
    async fetch() {
      this.park = await this.$content('park')
        .only( ['Suburb', 'Park', 'Fenced', 'Agility area', 'Dog water bubbler', 'Poo Bag dispenser', 'Swimming area'] )
        .search(this.q)
        .fetch()
    }
  }
    
</script>