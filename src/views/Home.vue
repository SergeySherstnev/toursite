<template>
  <div class="home">
    <div v-for="tour of tours" v-bind:key="tour.id">
<!--      <v-flex class="pa-4">-->
        <tour-brief-card :tourInfo="tour"/>
<!--      </v-flex>-->
    </div>
  </div>
</template>

<script>
  // @ is an alias to /src
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
  }
</script>
