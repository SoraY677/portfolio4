<template>
  <ul class="d-flex justify-sm-space-between">
    <li v-for="item in linkList" :key="item.id">
      <a :href="item.url" class="d-inline-block">
        <img :src="item.path" />
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    linkList: Array,
  },
};
</script>

<style scoped>
li {
  display: flex;
  justify-content: center;
}

a {
  display: inline-block;
  height: 100%;
}

img {
  height: 100%;
}
</style>
