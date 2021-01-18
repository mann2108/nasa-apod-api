<template>
  <v-card class="mx-auto" height="80vh" width="100vh">
    <v-img
      class="white--text align-end"
      height="80vh"
      width="100vh"
      :src="dataURL"
      v-if="dataType === 'image'"
    >
    </v-img>
    <iframe
      v-else
      :src="dataURL"
      height="100%"
      width="100%"
      frameBorder="0"
      allow="autoplay; encrypted-media"
      allowFullScreen
      title="video"
    />
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
  props: ["dataURL", "dataType"],
  name: "Card",
};
</script>
<style scoped></style>
