<template>
  <ul class="d-flex justify-center pa-0 mx-16 mx-sm-0 link-container">
    <li v-for="item in linkList" :key="item.id">
      <a :href="item.url" class="d-inline-block px-2">
        <img :src="item.path" :alt="item.altName" width="60" height="60" />
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
.link-container {
  max-height: 50px;
}

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
  height: 100%;
}
</style>
