<template>
  <v-container fluid fill-height id="home-page">
    <div v-for="tour of tours" v-bind:key="tour.id">
        <tour-brief-card :tourInfo="tour"
                         @click="openDetailedCard(key)"/>
    </div>
  </v-container>
</template>

<script>
  // @ is an alias to /src
  import { EventBus } from '@/event-bus.js'
  import TourBriefCard from '@/components/TourBriefCard.vue'

  export default {
    name: 'home',
    components: {
      TourBriefCard,
    },
    data: () => ({
      'tours': [{
        id: 0,
        title: 'Top 10 Australian beaches',
        subtitle: 'Number 10',
        picture: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
      },
        {
          id: 1,
          title: 'City Tour',
          subtitle: 'Number 1',
          picture: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
        },
        {
          id: 2,
          title: 'Peterhof',
          subtitle: 'Number 2',
          picture: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
        }],
    }),
    methods: {
          openDetailedCard (id) {
            console.log(id)
            //EventBus.$emit(id)
          }
        }
  }
</script>
