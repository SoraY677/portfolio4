<template>
  <section>
    <swipe-suggest></swipe-suggest>
    <work-list :workList="workList"></work-list>
  </section>
</template>

<script>
import SwipeSuggest from "@/components/BaseModule/SwipeSuggest.vue";
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
            "Nuxt.jsの勉強も兼ねて制作したWebサイトです。",
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
          title: "Timiデート",
          category: "フロントエンド",
          tagList: ["Vue.js", "Nuxt.js", "Tailwind.css"],
          detail: [
            "友人のつてで紹介いただいた、学生が運営する会社「Timifura」のデート提案システム開発でフロントエンドを担当しました。",
            "およそ60ページのWebサイトを1人で2か月程で仕上げました。",
            "大きなプロジェクトに参加したことが初めてであったため、納期に追われながら何とか完成までもっていくことができました。",
          ],
          img: {
            path: "/work/timi-date.jpg",
            altName: "Timiデート画像",
          },
          link: {
            name: "Timifura",
            path: "",
          },
        },
        {
          title: "大谷研究室コンペ2019",
          category: "AI",
          tagList: ["C++", "人工蜂コロニーアルゴリズム"],
          detail: [
            "私の所属する研究室で3年時に行われた最適化問題です。",
            "同研究室の学部3年生同士でコンペティション形式の施設建設位置の最適化を行いました。",
            "計9人の研究生の中で最も良い結果を出し、優勝しました！",
          ],
          img: {
            path: "/work/otani-comp.jpg",
            altName: "大谷研究室コンペの画像",
          },
          link: {
            name: "ソースコード",
            path:
              "https://github.com/SoraY677/Otanilab_ECACompetition2019_BeeColony",
          },
        },
        {
          title: "【卒業研究】TexasHoldem with AI",
          category: "フロントエンド+AI",
          tagList: ["javascript", "多数決機械(NN)", "webpack", "node.js"],
          detail: [
            "私の所属する研究室での卒業研究作品です。",
            "コンピュータの表情とプレイヤの表情をそれぞれ使ってポーカーをすることで、駆け引きを楽しむことができます！",
            "また、多数決機械というニューラルネットワークを組み込んだので、AIがプレイヤの行動を学習し、常に成長します。",
          ],
          img: {
            path: "/work/texasholdem.jpg",
            altName: "TexasHoldem with AIの画像",
          },
          link: {
            name: "ゲームをプレイ",
            path: "",
          },
        },
      ],
    };
  },
  components: {
    SwipeSuggest,
    WorkList,
  },
};
</script>

<style scoped>
</style>
