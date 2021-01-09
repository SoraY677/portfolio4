<template>
  <div class="square" :class="{ circle: isCircle }">
    <div class="square-inner">
      <div class="content">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isCircle: false,
  },
};
</script>

<style scoped>
.square {
  position: relative;
  width: 100%;
  height: 0;
  padding-top: 100%;
  overflow: hidden;
}

.circle {
  border-radius: 50%;
}

.square-inner {
  position: absolute;
  display: flex;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  justify-content: center;
  align-items: center;
}

.content {
  position: relative;
  width: 100%;
  height: 100%;
}
</style>
