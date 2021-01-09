<template>
  <header class="text-h3 text-md-h1">
    <div class="header-inner">
      <square-block :isCircle="true">
        <div class="circle-container">
          <h1 class="text-title-font text-bg-color">
            {{ $route.name }}
          </h1>
        </div>
      </square-block>
    </div>
  </header>
</template>

<script>
import SquareBlock from "@/components/BaseModule/SquareBlock";
export default {
  components: {
    SquareBlock,
  },
};
</script>

<style scoped>
header {
  position: relative;
  width: 100%;
  height: 20vw;
  font-size: 2em;
}

.header-inner {
  position: absolute;
  width: 140vw;
  top: -120vw;
  left: -20vw;
}

.circle-container {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  width: 100%;
  height: 100%;
  background-color: var(--main-color);
}

h1 {
  font-size: 2em;
  margin-bottom: 10px;
}
</style>
