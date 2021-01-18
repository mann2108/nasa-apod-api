<template>
  <v-card class="mx-auto" height="80vh" width="100vh">
    <v-img
      class="white--text align-end"
      height="80vh"
      width="100vh"
      :src="imageURL"
    >
    </v-img>
    <v-card-title><slot name="title"/></v-card-title>
    <v-card-subtitle class="pb-0"> <slot name="date"/></v-card-subtitle>
    <v-card-text class="text--primary">
      <h4>Explanation : -</h4>
      <div><slot name="explanation" /></div>
    </v-card-text>
  </v-card>
</template>
<script>
export default {
  props: ["imageURL"],
  name: "Card",
};
</script>
<style scoped></style>
