<template>
  <v-container fluid fill-height id="home-page" align-start>
    <div v-for="tour of tours" v-bind:key="tour.id">
        <tour-brief-card :tourInfo="tour"
                         @click="openDetailedCard(tour.id)"/>
    </div>
    <tour-detail-card ref="detailDialog"/>
  </v-container>
</template>

<script>
  // @ is an alias to /src
  // import { EventBus } from '@/event-bus.js'
  import TourBriefCard from '@/components/TourBriefCard.vue'
  import TourDetailCard from '@/components/TourDetailCard.vue'

  export default {
    name: 'home',
    components: {
      TourBriefCard,
      TourDetailCard
    },
    data: () => ({
      'tours': [{
        id: 0,
        title: 'Ermitazh',
        subtitle: 'Number 10',
        description: 'Description',
        score: 4,
        scoreTotal: 113,
        picture: 'images/' + 'Ermitazh',
      },
        {
          id: 1,
          title: 'City Tour',
          subtitle: 'Number 1',
          description: 'Description',
          score: 4,
          scoreTotal: 113,
          picture: 'images/' + 'petersburg',
        },
        {
          id: 2,
          title: 'Peterhof',
          subtitle: 'Number 2',
          description: 'Description',
          score: 4,
          scoreTotal: 113,
          picture: 'images/' + 'peterhof',
        }],
    }),
    methods: {
          openDetailedCard (id) {
            console.log(id)
            this.$refs.detailDialog.open(this.tours[id])
            // EventBus.$emit(id)
          }
        }
  }
</script>
