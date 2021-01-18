<template>
  <v-container>
    <slot name="header"></slot>
    <!-- Loader -->
    <v-container v-if="isAPIFetchSuccessful === null">
      <loader>
        <h3 slot="message">Loading...</h3>
      </loader>
    </v-container>
    <!-- Show on successful fetch -->
    <v-container v-if="isAPIFetchSuccessful === false">
      <loader>
        <v-overlay slot="overlay" :absolute="absolute" :value="overlay">
          <h1 id="overlayMessage">Error Occured While Fetching Data</h1>
        </v-overlay>
      </loader>
    </v-container>
    <!-- Show on unsuccessful fetch -->
    <v-container
      v-if="isAPIFetchSuccessful === true"
      class="fill-height"
      fluid
      style="max-height: 100vh"
    >
      <v-fade-transition mode="out-in">
        <v-row>
          <v-col cols="12">
            <card :imageURL="data.url">
              <p slot="title">{{ data.title }}</p>
              <p slot="date">{{ data.date }}</p>
              <p slot="explanation">{{ data.explanation }}</p>
            </card>
          </v-col>
        </v-row>
      </v-fade-transition>
    </v-container>
  </v-container>
</template>

<script>
import Loader from "./Loader";
import Card from "./Card";
export default {
  name: "NASA_API",
  components: {
    loader: Loader,
    card: Card,
  },
  data: () => ({
    data: null,
    api:
      "https://api.nasa.gov/planetary/apod?api_key=KOAVjU96q4a8PWary2YJQewHCgf2e9HbhSxCq20c",
    isAPIFetchSuccessful: null,
    absolute: true,
    overlay: true,
  }),
  created() {
    this.axios
      .get(this.api)
      .then((response) => {
        this.data = response.data;
        this.isAPIFetchSuccessful = true;
      })
      .catch(() => {
        this.isAPIFetchSuccessful = false;
      });
  },
};
</script>

<style scoped>
#overlayMessage {
  color: black;
}
</style>
