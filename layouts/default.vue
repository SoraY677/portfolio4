<template>
  <v-app>
    <l-menu></l-menu>
    <my-header class="mb-16"></my-header>
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
