<template>
  <ul class="d-flex justify-space-between pa-0 mx-16 mx-sm-0">
    <li v-for="item in linkList" :key="item.id">
      <a :href="item.url" class="d-inline-block px-2">
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
  width: 100%;
}
</style>
