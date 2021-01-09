<template>
  <section>
    <my-header class="mb-16 mb-sm-15"></my-header>
    <my-form class="mx-5 mb-10"></my-form>
  </section>
</template>

<script>
import MyHeader from "@/components/TheHeader.vue";
import MyForm from "@/components/contact/TheForm.vue";
export default {
  components: {
    MyHeader,
    MyForm,
  },
};
</script>

<style scoped>
</style>
