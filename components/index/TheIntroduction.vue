<template>
  <v-container class="d-flex justify-space-around align-center">
    <img src="alien.svg" class="icon" alt="宇宙人の頭" />
    <div class="text-container">
      <div class="pa-3">
        <p
          v-for="text in introText"
          :key="text.id"
          class="text-body-1 text-sm-h6"
        >
          {{ text }}
        </p>
      </div>
    </div>
  </v-container>
</template>

<script>
export default {
  props: {
    introText: Array,
  },
};
</script>

<style scoped>
.icon {
  width: 20%;
  height: 120px;
}

.text-container {
  width: 68%;
  border: 4px solid var(--main-color);
  border-radius: 1em;
}
</style>
