<template>
  <section>
    <key-visual :linkList="linkList" class="mb-12"></key-visual>
    <intro :introText="introText" class="px-2 mb-12"></intro>
    <skill class="px-16 l-skill mb-12" :skillList="skillList"></skill>
  </section>
</template>

<script>
import KeyVisual from "@/components/index/TheKeyVisual.vue";
import Intro from "@/components/index/TheIntroduction.vue";
import Skill from "@/components/index/TheSkillList.vue";
export default {
  components: {
    KeyVisual,
    Intro,
    Skill,
  },
  data() {
    return {
      linkList: [
        {
          name: "twitter",
          url: "https://twitter.com/TenYDGB",
          path: "/link/twitter.svg",
          altName: "Twitterアイコン",
        },
        {
          name: "Github",
          url: "https://github.com/SoraY677",
          path: "/link/github.svg",
          altName: "Githubアイコン",
        },
        {
          name: "Qiita",
          url: "https://qiita.com/SoraYamaguchi",
          path: "/link/qiita.svg",
          altName: "Qiitaアイコン",
        },
      ],
      introText: [
        "こんにちは。ワタシはヤマグチソラです",
        "宇宙生まれ地球育ち。",
        "ギークなやつは大体トモダチ。",
        "人間で言うと22サイのオトコノコ",
      ],
      skillList: [
        {
          name: "フロントエンド",
          path: "/frontend.svg",
          altName: "フロントエンド",
        },
        {
          name: "AI",
          path: "/AI.svg",
          altName: "AI",
        },
        {
          name: "ツール",
          path: "/tool.svg",
          altName: "ツール",
        },
        {
          name: "バックエンド",
          path: "/backend.svg",
          altName: "バックエンド",
        },
      ],
    };
  },
};
</script>

<style scoped>
.l-skill {
  max-width: 800px;
  margin: auto;
}
</style>
