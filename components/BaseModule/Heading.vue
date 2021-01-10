<template>
  <h1 class="px-1 px-sm-8">
    <slot></slot>
  </h1>
</template>

<script>
export default {};
</script>

<style scoped>
h1 {
  width: fit-content;
  margin: 0 auto;
  text-align: center;
  font-size: 1.4em;
  border-bottom: 2px solid var(--main-color);
}
</style>
