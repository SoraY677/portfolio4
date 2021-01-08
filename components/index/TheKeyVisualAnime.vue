<template>
  <v-container class="d-flex m-container">
    <img src="/pirot.svg" class="pirot-img" />
    <img
      src="/hand.svg"
      class="hand-img"
      v-anime="{
        rotate: {
          value: 55,
          duration: 1000,
        },
        easing: 'easeInOutQuad',
        direction: 'alternate',
        loop: true,
      }"
    />
  </v-container>
</template>

<script>
export default {};
</script>

<style scoped>
.m-container {
  height: 140px;
}
.pirot-img {
  width: 5em;
  height: 100%;
}

.hand-img {
  width: 2em;
  margin-top: 10%;
}
</style>
