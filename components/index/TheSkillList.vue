<template>
  <section class="grid">
    <h1 class="text-center text-h1 d-sm-none">イロイロデキマス！</h1>
    <div :class="{ 'outer-line': !$vuetify.breakpoint.smAndUp }" class="pa-3">
      <v-row justify="center" class="my-0">
        <v-col cols="12" sm="4"
          ><skill-circle :skill="skillList[0]"></skill-circle
        ></v-col>
      </v-row>
      <v-row class="my-0">
        <v-col cols="12" sm="4"
          ><skill-circle :skill="skillList[1]"></skill-circle
        ></v-col>
        <v-col cols="12" sm="4" class="d-none d-sm-block"
          ><skill-circle
            :isText="true"
            :text="['イロイロ', 'デキマス']"
          ></skill-circle
        ></v-col>
        <v-col cols="12" sm="4"
          ><skill-circle :skill="skillList[2]"></skill-circle
        ></v-col>
      </v-row>
      <v-row justify="center" class="my-0">
        <v-col cols="12" sm="4"
          ><skill-circle :skill="skillList[3]"></skill-circle
        ></v-col>
      </v-row>
    </div>
  </section>
</template>

<script>
import SkillCircle from "@/components/index/TheSkillListCircle";
export default {
  props: {
    skillList: Array,
  },
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
