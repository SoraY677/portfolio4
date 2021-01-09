<template>
  <section class="work-container">
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
    <a :href="work.link.path" class="img-container ml-5">
      <div class="img-cover">{{ work.link.name }}(外部リンク)</div>
      <img
        :src="work.img.path"
        :alt="work.img.altName"
        width="640"
        height="300"
      />
    </a>
  </section>
</template>

<script>
export default {
  props: {
    work: Object,
  },
};
</script>

<style scoped>
.work-container {
  display: flex;
  height: 100%;
  justify-content: space-between;
  overflow-x: scroll;
  border: 2px solid var(--main-color);
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

h1 {
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
