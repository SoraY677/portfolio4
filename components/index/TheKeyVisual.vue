<template>
  <v-card min-height="300px" class="key-visual">
    <v-container class="pa-16">
      <!-- 名前 -->
      <div>
        <name></name>
      </div>
      <!-- 宇宙飛行士のアニメーション -->
      <div class="d-flex justify-end">
        <anime class="pirot"></anime>
      </div>
    </v-container>
    <div class="circle-block"></div>
  </v-card>
</template>

<script>
import name from "@/components/index/TheKeyVisualName";
import anime from "@/components/index/TheKeyVisualAnime";
export default {
  components: {
    name,
    anime,
  },
};
</script>

<style scoped>
.key-visual {
  background-color: var(--main-color);
  color: var(--bg-color);
}

.circle-block {
  position: absolute;
  width: 200px;
  height: 200px;
  border-radius: 50% !important;
  left: 50%;
  transform: translateX(-50%);
  background-color: var(--main-color);
  color: var(--bg-color);
}

.pirot {
  width: fit-content;
  margin: 0;
}
</style>
