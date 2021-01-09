<template>
  <div class="d-flex work-list-container">
    <div class="left-side"></div>

    <ul class="px-0">
      <li v-for="work in workList" :key="work.id">
        <item :work="work"></item>
      </li>
    </ul>
  </div>
</template>

<script>
import Item from "@/components/work/TheWorkListItem";
export default {
  props: {
    workList: Array,
  },
  components: {
    Item,
  },
};
</script>

<style scoped>
.work-list-container {
  border-top: 2em solid var(--main-color);
  border-bottom: 2em solid var(--main-color);
}

.left-side {
  width: 10%;
  background-color: var(--main-color);
}

ul {
  width: 90%;
}

li {
  height: 340px;
  list-style: none;
}
</style>
