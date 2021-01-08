<template>
  <v-card class="key-visual" min-height="300px" elevation="0">
    <div class="pa-3 pa-sm-16 key-visual-inner text-h5 text-sm-h2">
      <!-- 名前 -->
      <div>
        <name></name>
      </div>
      <!-- 宇宙飛行士のアニメーション -->
      <div class="d-flex justify-end">
        <anime class="pirot"></anime>
      </div>
    </div>
    <v-row justify="end" class="ornament px-5">
      <v-col cols="12" sm="4" class="pa-0 d-flex justify-center"
        ><div class="circle-block">
          <span class="d-block pb-1">scroll</span>
          <p class="scroll-arrow"></p></div
      ></v-col>
      <v-col cols="12" sm="4" class="pa-0"
        ><link-list :linkList="linkList" class="link-list mt-5"></link-list
      ></v-col>
    </v-row>
  </v-card>
</template>

<script>
import name from "@/components/index/TheKeyVisualName";
import anime from "@/components/index/TheKeyVisualAnime";
import LinkList from "@/components/index/TheKeyVisualLink";
export default {
  components: {
    name,
    anime,
    LinkList,
  },
  props: {
    linkList: Array,
  },
};
</script>

<style scoped>
.key-visual {
  color: var(--bg-color);
}

.key-visual-inner {
  width: 100%;
  background-color: var(--main-color);
}
.pirot {
  z-index: 100;
  width: fit-content;
  margin: 0;
}

.ornament {
  width: 100%;
}

.circle-block {
  display: flex;
  left: 50%;
  width: 200px;
  height: 100px;
  border-radius: 0 0 100px 100px;
  justify-self: center;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
  flex-wrap: wrap;
  background-color: var(--main-color);
  color: var(--bg-color);
}
.scroll-arrow {
  height: 3em;
  width: 1em;
  border-left: 2px solid var(--bg-color);
  border-bottom: 2px solid var(--bg-color);
  margin: 0;
  transform: skewY(-45deg) translateX(50%);
}
</style>
