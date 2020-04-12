<template>
  <v-dialog v-model="dialog"
              persistent no-click-animation @keydown.esc="close"
              scrollable
              max-width="800px">
    <v-card>
      <v-img :src="tourInfo.picture + '_large.jpg'"></v-img>
      <v-card-title class="justify-center">{{ tourInfo.title }}</v-card-title>

      <v-card-text>
        <v-row  justify="end"
                align="center"
                class="mx-0">
          <v-rating :value=tourInfo.score
                    color="amber"
                    dense
                    half-increments
                    readonly
                    size="14"></v-rating>

          <div class="grey--text ml-4">{{ tourInfo.score }} ({{ tourInfo.scoreTotal }})</div>
        </v-row>

        <div>{{ tourInfo.description }}</div>
      </v-card-text>

      <v-divider class="mx-4"></v-divider>

      <v-card-title>Available dates</v-card-title>

      <v-card-text>
        <v-chip-group
          v-model="selection"
          active-class="deep-purple accent-4 white--text"
          column>
            <v-chip label>5:30PM</v-chip>
            <v-chip label>7:30PM</v-chip>
            <v-chip label>8:00PM</v-chip>
            <v-chip label>9:00PM</v-chip>
        </v-chip-group>
      </v-card-text>

      <v-card-actions>
        <v-btn color="orange" text>Reserve</v-btn>
        <v-btn color="orange" text @click="openCalendar">Calendar</v-btn>
        <v-spacer/>
        <v-btn color="orange" text @click="close">Back</v-btn>
      </v-card-actions>
    </v-card>

    <calendar ref="calendar"/>

  </v-dialog>
</template>

<script>
  import Calendar from '@/components/TourCalendar.vue'

  export default {
    name: 'TourDetailCard',
    components: {
      Calendar
    },
    data: () => ({
      dialog: false,
      tourInfo: {
          title: 'Title',
          subtitle: 'Subtitle',
          description: 'Description',
          picture: 'images/' + 'peterhof_large.jpg',
      },
      selection: 1
    }),

    methods: {
      open (item) {
          console.log('Info: ')
          console.log(item)
          this.tourInfo = Object.assign({}, item)
          this.dialog = true
      },
      openCalendar () {
          this.$refs.calendar.open()
      },
      close () {
          this.dialog = false
      },
    },
  }
</script>
