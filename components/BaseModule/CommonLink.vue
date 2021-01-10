<template>
  <div class="common-link-outer" href="Contact">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.common-link-outer {
  display: flex;
  justify-content: center;
  width: 100%;
}

.common-link-outer > * {
  position: relative;
  z-index: 100;
  display: block;
  padding: 0.2em;
  font-size: 2em;
  border-radius: 1em;
  color: var(--main-color);
  text-decoration: none;
  text-align: center;
  font-weight: bold;
  overflow: hidden;
  transition-duration: 0.3s;
  box-shadow: 2px 2px 5px 2px var(--main-color);
}

.common-link-outer > *::before {
  position: absolute;
  z-index: -1;
  content: "";
  top: 0;
  left: -110%;
  width: 120%;
  height: 100%;
  background-color: var(--main-color);
  transition-duration: 0.8s;
  transform: skew(45deg);
}

.common-link-outer > *:hover {
  color: var(--bg-color);
}

.common-link-outer > *:hover::before {
  left: 10%;
}
</style>
