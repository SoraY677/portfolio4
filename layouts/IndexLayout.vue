<template>
  <v-app>
    <l-menu></l-menu>
    <nuxt></nuxt>
    <my-footer class="mt-16"></my-footer>
  </v-app>
</template>

<script>
import MyHeader from "@/components/TheHeader.vue";
import LMenu from "~/layouts/Menu.vue";
import MyFooter from "@/components/TheFooter.vue";
export default {
  components: {
    MyHeader,
    LMenu,
    MyFooter,
  },
};
</script>

<style>
</style>
