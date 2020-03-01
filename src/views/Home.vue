<template>
  <v-container fluid fill-height id="home-page">
    <div v-for="tour of tours" v-bind:key="tour.id">
        <tour-brief-card :tourInfo="tour"
                         @click="openDetailedCard(key)"/>
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
        title: 'Top 10 Australian beaches',
        subtitle: 'Number 10',
        picture: 'images/' + 'Ermitazh_large.jpg',
      },
        {
          id: 1,
          title: 'City Tour',
          subtitle: 'Number 1',
          picture: 'images/' + 'petersburg_large.jpg',
        },
        {
          id: 2,
          title: 'Peterhof',
          subtitle: 'Number 2',
          picture: 'images/' + 'peterhof_large.jpg',
        }],
    }),
    methods: {
          openDetailedCard (id) {
            console.log(id)
            // this.$refs.detailDialog.open(this.tours[id])
            // EventBus.$emit(id)
          }
        }
  }
</script>
