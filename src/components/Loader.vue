<template>
  <v-container>
    <slot name="message"></slot>
    <slot name="overlay"></slot>
    <skeleton-loader />
  </v-container>
</template>
<script>
import SkeletonLoader from "./SkeletonLoader";
export default {
  name: "Loader",
  components: {
    "skeleton-loader": SkeletonLoader,
  },
};
</script>
<style scoped></style>
