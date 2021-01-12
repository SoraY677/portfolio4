<template>
  <section
    class="work-container"
    ref="item"
    onMouseDown="return false;"
    onSelectStart="return false"
  >
    <div class="detail-container pa-4">
      <div>
        <div class="d-flex title align-center pb-2">
          <h1>{{ work.title }}</h1>
          <v-chip class="ml-2" outlined>{{ work.category }}</v-chip>
        </div>
        <div class="d-flex mb-3">
          <p class="mb-0 d-flex align-end">使用した技術:</p>
          <ul class="d-flex pl-0 pt-1">
            <li v-for="tag in work.tagList" :key="tag" class="px-2">
              <v-chip>{{ tag }}</v-chip>
            </li>
          </ul>
        </div>
      </div>
      <div class="text-container">
        <p v-for="text in work.detail" :key="text.id" class="mb-2">
          {{ text }}
        </p>
      </div>
    </div>
    <div class="img-container ml-5">
      <img
        :src="work.img.path"
        :alt="work.img.altName"
        width="676"
        height="353"
        v-lazy-load
      />
    </div>
  </section>
</template>

<script>
export default {
  props: {
    work: Object,
    isSwipe: false,
  },
  mounted() {
    const DOM = this.$refs.item;
    let previousX = 0;
    let currentX = 0;
    DOM.addEventListener("mousedown", function (e) {
      this.isSwipe = true;
      previousX = e.clientX;
    });
    DOM.addEventListener("mousemove", function (e) {
      if (this.isSwipe == true) {
        currentX = e.clientX;
        DOM.scrollBy(-(currentX - previousX), 0);
        previousX = currentX;
      }
    });
    DOM.addEventListener("mouseup", function (e) {
      this.isSwipe = false;
      previousX = 0;
      currentX = 0;
    });
    DOM.addEventListener("mouseout", function (e) {
      this.isSwipe = false;
      previousX = 0;
      currentX = 0;
    });
  },
};
</script>

<style scoped>
.work-container {
  display: flex;
  height: 100%;
  justify-content: space-between;
  overflow-x: scroll;
  overflow-y: hidden;
  border: 2px solid var(--main-color);
  background-color: var(--bg-color);
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.detail-container {
  max-width: 40em;
  word-break: keep-all;
}

.title {
  border-bottom: 2px solid var(--main-color);
}

.img-container {
  position: relative;
  display: block;
  height: 100%;
}
.text-container {
  word-break: break-word;
}

.img-cover {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  color: var(--bg-color);
  background-color: rgba(79, 79, 115, 0.5);
  transition-duration: 0.3s;
}

.img-container:hover > .img-cover {
  opacity: 1;
}

img {
  height: 100%;
}
</style>
