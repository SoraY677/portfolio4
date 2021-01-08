<template>
  <v-app>
    <l-menu></l-menu>
    <nuxt></nuxt>
  </v-app>
</template>

<script>
import LMenu from "~/layouts/Menu.vue";
export default {
  components: {
    LMenu,
  },
};
</script>

<style>
</style>
