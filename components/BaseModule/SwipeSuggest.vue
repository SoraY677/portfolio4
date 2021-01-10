<template>
  <div class="suggest-container">
    <p>swipe to side-scroll</p>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.suggest-container {
  display: flex;
  justify-content: center;
}

p {
  position: relative;
  height: 1.5em;
  width: fit-content;
  font-weight: bold;
}

p::before,
p::after {
  position: absolute;
  content: "";
  top: 80%;
  left: -25%;
  width: 150%;
  height: 50%;
}

p::before {
  transform: skewX(45deg);
  border-bottom: 2px solid var(--main-color);
  border-right: 2px solid var(--main-color);
}

p::after {
  transform: skewX(-45deg);
  border-bottom: 2px solid var(--main-color);
  border-left: 2px solid var(--main-color);
}
</style>
