<template>
  <v-app>
    <v-main>
      <nasa-api>
        <v-app-bar app color="dark" dark slot="header">
          <div class="d-flex align-center">
            <v-img
              alt="Nasa Logo"
              class="shrink mr-2"
              contain
              src="https://www.nasa.gov/sites/all/themes/custom/nasatwo/images/nasa-logo.svg"
              transition="scale-transition"
              width="40"
              height="50"
            />
            <h2>NASA APOD API</h2>
          </div>
        </v-app-bar>
      </nasa-api>
    </v-main>
  </v-app>
</template>

<script>
import API from "./components/API";

export default {
  name: "NASA_API",
  components: {
    "nasa-api": API,
  },
  data: () => ({}),
};
</script>
<style></style>
