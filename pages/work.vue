<template>
  <section>
    <my-header class="mb-16 mb-sm-15"></my-header>
    <work-list :workList="workList"></work-list>
  </section>
</template>

<script>
import MyHeader from "@/components/TheHeader.vue";
import WorkList from "@/components/work/TheWorkList.vue";
export default {
  data() {
    return {
      workList: [
        {
          title: "Portfolio",
          category: "フロントエンド",
          tagList: ["Vue.js", "Nuxt.js", "Vuetify", "anime.js"],
          detail: [
            "Nuxt.jsの勉強も兼ねて制作し他Webサイトです。",
            "自身の名前が宇宙に由来することから、どうにか名前を憶えてほしくて宇宙をコンセプトにしました！",
            "私の特技や制作した作品を掲載していくので、このサイトを機に私のことを知っていただければ幸いです。",
          ],
          img: {
            path: "/work/portfolio.jpg",
            altName: "ポートフォリオ画像",
          },
          link: {
            name: "ホームページ",
            path: "https://soray677-portfolio.netlify.app",
          },
        },
        {
          title: "Portfolio",
          category: "フロントエンド",
          tagList: ["Vue.js", "Nuxt.js", "Vuetify", "anime.js"],
          detail: [
            "Nuxt.jsの勉強も兼ねて制作し他Webサイトです。",
            "自身の名前が宇宙に由来することから、どうにか名前を憶えてほしくて宇宙をコンセプトにしました！",
            "私の特技や制作した作品を掲載していくので、このサイトを機に私のことを知っていただければ幸いです。",
          ],
          img: {
            path: "/work/portfolio.jpg",
            altName: "ポートフォリオ画像",
          },
          link: {
            name: "ホームページ",
            path: "https://soray677-portfolio.netlify.app",
          },
        },
      ],
    };
  },
  components: {
    MyHeader,
    WorkList,
  },
};
</script>

<style scoped>
</style>
