<template>
  <v-app>
    <l-menu></l-menu>
    <nuxt></nuxt>
  </v-app>
</template>

<script>
import MyHeader from "@/components/TheHeader.vue";
import LMenu from "~/layouts/Menu.vue";
export default {
  components: {
    MyHeader,
    LMenu,
  },
};
</script>

<style>
</style>
