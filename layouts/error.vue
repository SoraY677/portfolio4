<template>
  <section>
    <div class="circle-outer">
      <square-block :isCircle="true" class="square-cover">
        <div class="circle-inner d-flex justify-center align-start"></div>
      </square-block>
      <div class="bottom-block">
        <div class="text-container mt-4">
          <h1 class="text-center mb-6">404 not Found</h1>
          <div class="text-center">
            <p>お探しのページは見つかりませんデシタ。</p>
            <p>ページのURLがマチガッテイル可能性がありマス。</p>
            <nuxt-link to="/"
              >お手数ですが、トップページへお戻りクダサイ。</nuxt-link
            >
          </div>
        </div>
        <footer>
          <p class="text-center">© 2020 Sora Yamaguchi All Rights Reserved</p>
        </footer>
      </div>
    </div>
  </section>
</template>

<script>
import SquareBlock from "@/components/BaseModule/SquareBlock";
export default {
  layout: "ErrorLayout",
  components: {
    SquareBlock,
  },
};
</script>

<style scoped>
.circle-outer {
  width: 300%;
}

.square-cover {
  position: absolute;
  width: 200%;
  top: 20%;
  left: -50%;
}

.circle-inner {
  position: relative;
  width: 100%;
  height: 100%;
  background-color: var(--main-color);
}

.bottom-block {
  position: absolute;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  top: 30%;
  height: 100vh;
  width: 100%;
  background-color: var(--main-color);
}

.text-container {
  width: 100vw;
  color: var(--bg-color);
}

footer {
  color: var(--bg-color);
  width: 100%;
}
</style>
