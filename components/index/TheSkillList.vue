<template>
  <section class="grid pa-5">
    <h1 class="text-center text-h1 d-sm-none">イロイロデキマス！</h1>
    <div
      :class="{ 'outer-line': !$vuetify.breakpoint.smAndUp }"
      class="pa-3 text"
    >
      <v-row justify="center" class="my-0">
        <v-col cols="12" sm="4"><skill-circle></skill-circle></v-col>
      </v-row>
      <v-row class="my-0">
        <v-col cols="12" sm="4"><skill-circle></skill-circle></v-col>
        <v-col cols="12" sm="4" class="d-none d-sm-block"
          ><skill-circle
            :isText="true"
            :text="['イロイロ', 'デキマス']"
          ></skill-circle
        ></v-col>
        <v-col cols="12" sm="4"><skill-circle></skill-circle></v-col>
      </v-row>
      <v-row justify="center" class="my-0">
        <v-col cols="12" sm="4"><skill-circle></skill-circle></v-col>
      </v-row>
    </div>
  </section>
</template>

<script>
import SkillCircle from "@/components/index/TheSkillListCircle";
export default {
  components: {
    SkillCircle,
  },
};
</script>

<style scoped>
.outer-line {
  border: 3px solid var(--main-color);
  border-radius: 30px;
}
</style>
