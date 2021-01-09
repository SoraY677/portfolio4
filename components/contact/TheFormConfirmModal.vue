<template>
  <div>
    <v-dialog v-model="isOpen" persistent max-width="290">
      <v-card>
        <v-card-title class="text-h4">内容確認</v-card-title>
        <v-card-text class="text-content">
          <p class="mb-2">
            <span class="sub-title">name</span>
            <span class="text-h5">{{ content.name }}</span>
          </p>

          <p class="mb-2">
            <span class="sub-title">mail adress</span>
            <span class="text-h5">{{ content.mailadress }}</span>
          </p>

          <p class="mb-2">
            <span class="sub-title">Content</span>
            <span class="text-h5">{{ content.content }}</span>
          </p>
        </v-card-text>
        <v-card-actions>
          <v-btn color="secondary" @click="cancel"> キャンセル </v-btn>
          <v-btn color="primary" @click="send"> 送信！</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-dialog v-model="isConfirm">
      <v-card>
        <v-card-title>送信完了</v-card-title>
        <v-card-text></v-card-text>
        <v-card-actions>
          <v-btn color="green darken-1" text @click="isConfirm = false">
            OK!
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isConfirm: false,
    };
  },
  props: {
    content: Object,
    isOpen: false,
  },
  methods: {
    cancel() {
      this.$emit("change", false);
    },
    send() {
      this.$emit("change", false);
      this.isConfirm = true;
    },
  },
};
</script>

<style scoped>
.text-content {
  color: var(--main-color) !important;
}

.sub-title {
  display: block;
  width: fit-content;
  padding: 0.1em 0.3em;
  margin-bottom: 0.2em;
  border: 1px solid var(--main-color);
}
</style>
