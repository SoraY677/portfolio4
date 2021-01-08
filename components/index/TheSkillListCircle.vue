<template>
  <div>
    <div
      class="base"
      :class="{
        'common-circle': $vuetify.breakpoint.smAndUp,
      }"
    >
      <div
        :class="{
          'common-circle-inner': $vuetify.breakpoint.smAndUp,
        }"
      >
        <!-- テキスト -->
        <h1
          v-if="isText"
          class="container-block intro-text"
          :class="{ outline: isText }"
        >
          <p v-for="t in text" :key="t.id" class="text-center my-0">
            {{ t }}
          </p>
        </h1>
        <!-- スキル -->
        <div
          class="container-block"
          :class="{ 'rect-block': !$vuetify.breakpoint.smAndUp }"
          v-else
        >
          <img src="/frontend.svg" />
          <div class="text">
            <p>フロントエンド</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isText: false,
    text: Array,
  },
};
</script>

<style scoped>
.base {
  background-color: var(--main-color);
  color: var(--bg-color);
}

.container-block {
  display: flex;
  width: 100%;
  height: 100%;
  justify-content: center;
  flex-direction: column;
}

.outline {
  background-color: var(--bg-color);
  color: var(--main-color);
  border: 5px solid var(--main-color);
  border-radius: 50%;
}

.rect-block {
  width: 100%;
  height: 200px;
}

img {
  height: 50%;
}

.text {
  font-size: 0.8em;
  text-align: center;
}

.intro-text {
  font-size: 0.8em;
  font-weight: bold;
}
</style>
