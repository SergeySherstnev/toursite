<template>
  <v-dialog v-model="dialog"
              persistent no-click-animation @keydown.esc="close"
              @click:outside="close"
              max-width="800px">
    <v-card
      class="mx-auto my-12"
      max-width="374"
    >
      <v-img
        height="250"
        src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
      ></v-img>

      <v-card-title>Excursion name</v-card-title>

      <v-card-text>
        <v-row
          align="center"
          class="mx-0"
        >
          <v-rating
            :value="4.5"
            color="amber"
            dense
            half-increments
            readonly
            size="14"
          ></v-rating>

          <div class="grey--text ml-4">4.5 (413)</div>
        </v-row>

        <div class="my-4 subtitle-1 black--text">
          100$ 4 / 15
        </div>

        <div>Excursion description</div>
      </v-card-text>

      <v-divider class="mx-4"></v-divider>

      <v-card-title>Available dates</v-card-title>

      <v-card-text>
        <v-chip-group
          v-model="selection"
          active-class="deep-purple accent-4 white--text"
          column
        >
          <v-chip>5:30PM</v-chip>

          <v-chip>7:30PM</v-chip>

          <v-chip>8:00PM</v-chip>

          <v-chip>9:00PM</v-chip>
        </v-chip-group>
      </v-card-text>

      <v-card-actions>
        <v-btn
          color="deep-purple accent-4"
          text
        >
          Reserve
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
  export default {
    name: 'TourDetailCard',
    props: ['tourInfo'],
    data: () => ({
      dialog: false,
      selection: 1
    }),

    methods: {
      open (tourInfo) {
          console.log('Info: ')
          console.log(tourInfo)
          this.dialog = true
      },
      close () {
          this.dialog = false
      },
    },
  }
</script>
