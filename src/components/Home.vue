<template>
    <div>

        <v-container fluid>
            <v-layout row>
                <v-flex xs12>
                    <v-carousel>
                    <v-carousel-item
                        v-for="ad in ads"
                        :key="ad.id"
                        :src="ad.imageSrc"

                    >
                        <div class="car-link">
                            <v-btn class="error" :to="'/ad/' + ad.id">{{ad.title}}</v-btn>
                        </div>
                    </v-carousel-item>
                    </v-carousel>
                </v-flex>
            </v-layout>
        </v-container>
        <v-container grid-list-lg>
            <v-layout row wrap>
                <v-flex
                        xs12
                        sm6
                        md4
                        v-for="ad in ads"
                        :key="ad.id"
                >
                    <v-card>
                        <v-card-media
                                :src="ad.imageSrc"
                                height="200px"
                        ></v-card-media>

                        <v-card-title primary-title>
                            <div>
                                <h3 class="headline mb-0">{{ad.title}}</h3>
                                <div>{{ad.description}}</div>
                            </div>
                        </v-card-title>

                        <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn flat :to="/ad/ + ad.id">Open</v-btn>
                            <v-btn flat class="primary">Buy</v-btn>
                        </v-card-actions>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>
    </div>
</template>

<script>
  export default {
    data () {
      return {
        ads: [
          {
            title: 'First ad',
            description: 'lorem lorem 5',
            promo: false,
            imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
            id: '123'
          },
          {
            title: '2 ad',
            description: 'lorem lorem 5',
            promo: false,
            imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
            id: '123'
          },
          {
            title: '3 ad',
            description: 'lorem lorem 5',
            promo: false,
            imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
            id: '123'
          },
        ]
      }
    }
  }
</script>

<style scoped>
    .car-link{
        position: absolute;
        bottom: 50px;
        left: 50%;
        background: rbga(0,0,0, .5);
        transform: translate(-50%, 0);
        padding: 5px 15px;
        border-top-right-radius: 5px;
        border-bottom-left-radius: 5px;
    }
</style>
