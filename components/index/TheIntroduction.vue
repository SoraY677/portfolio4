<template>
  <v-container class="d-flex justify-space-around">
    <img src="alien.svg" class="icon" />
    <div class="text-container">
      <p class="pa-3">{{ introText }}</p>
    </div>
  </v-container>
</template>

<script>
export default {
  props: {
    introText: "",
  },
};
</script>

<style scoped>
.icon {
  width: 20%;
}

.text-container {
  width: 68%;
  border: 4px solid var(--main-color);
  border-radius: 1em;
}
</style>
