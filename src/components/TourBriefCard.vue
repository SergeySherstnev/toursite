<template>
  <v-card class="ma-2"
          max-width="400">
    <v-img
      class="white--text align-end"
      height="200px"
      :src='tourInfo.picture'>
      <v-card-title>{{ tourInfo.title }}</v-card-title>
    </v-img>

    <v-card-subtitle class="pb-0">{{ tourInfo.subtitle }}</v-card-subtitle>

    <v-card-text class="text--primary">
      <div>Whitehaven Beach</div>

      <div>Whitsunday Island, Whitsunday Islands</div>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="orange"
        text
      >
        Share
      </v-btn>

      <v-btn
        color="orange"
        text
        @click="toConsole"
      >
        Explore
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
  export default {
    name: 'TourBriefCard',
    props: ['tourInfo'],
    data: () => ({
      // loading: false,
      // selection: 1,
    }),

    methods: {
      toConsole () {
        console.log('Info: ')
        console.log(this.tourInfo)
      },
    },
  }
</script>
