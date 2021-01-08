<template>
  <section>
    <key-visual :linkList="linkList" class="mb-12"></key-visual>
    <intro :introText="introText" class="px-12"></intro>
  </section>
</template>

<script>
import KeyVisual from "@/components/index/TheKeyVisual.vue";
import Intro from "@/components/index/TheIntroduction.vue";
export default {
  components: {
    KeyVisual,
    Intro,
  },
  data() {
    return {
      linkList: [
        {
          name: "twitter",
          url: "https://twitter.com/TenYDGB",
          path: "/link/twitter.svg",
        },
        {
          name: "Github",
          url: "https://github.com/SoraY677",
          path: "/link/github.svg",
        },
        {
          name: "Qiita",
          url: "https://qiita.com/SoraYamaguchi",
          path: "/link/qiita.svg",
        },
      ],
      introText: [
        "こんにちは。ワタシはヤマグチソラです",
        "宇宙生まれ地球育ち。",
        "ギークなやつは大体トモダチ。",
        "人間で言うと22サイのオトコノコ",
      ],
    };
  },
};
</script>

<style scoped>
</style>
