<template>
  <section
    class="mx-5 d-flex justify-center align-center flex-wrap text-h4 text-sm-h2"
  >
    <div class="text-container">
      <h1 class="mb-4">
        Under
        <span
          class="d-inline-block"
          v-anime="{
            translateX: 0,
            translateY: -10,
            duration: 1000,
            easing: 'easeInOutQuart',
            direction: 'alternate',
            loop: true,
          }"
          >🛸</span
        >
        Construction
      </h1>
      <div>
        <p>現在工事中デス...ゴメンナサイ！</p>
        <p>近日公開デス。コウ、ゴキタイ！</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
section {
  border: 3px solid var(--main-color);
  border-radius: 30px;
}

.text-container {
  font-size: 0.6em;
}
</style>
