<template>
  <v-container class="d-flex m-container">
    <img
      src="/pirot.svg"
      alt="宇宙飛行士"
      class="pirot-img"
      width="120"
      height="120"
    />
    <img
      src="/hand.svg"
      alt="宇宙飛行士の手"
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
      width="40"
      height="40"
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
