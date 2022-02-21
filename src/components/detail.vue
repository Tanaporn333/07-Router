<template>
  <v-container>
    <h5 class="text--secondary">{{ productid }}</h5>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      productid: this.$route.params.id,
    };
  },
};
</script>

<style>
</style>