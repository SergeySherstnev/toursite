<template>
  <v-dialog v-model="dialog"
              persistent no-click-animation @keydown.esc="close"
              max-width="500px">
    <v-card
    >
      <v-img
        :src='tourInfo.picture'
      ></v-img>

      <v-card-title>{{ tourInfo.title }}</v-card-title>

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

        <div>{{ tourInfo.description }}</div>
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
    // props: ['tourInfo'],
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
      close () {
          this.dialog = false
      },
    },
  }
</script>
