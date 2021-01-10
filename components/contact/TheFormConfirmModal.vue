<template>
  <div>
    <v-dialog v-model="isOpen" persistent max-width="290">
      <v-card>
        <v-card-title class="text-h4">内容確認</v-card-title>
        <v-card-text class="text-content">
          <p class="mb-4">
            <span class="sub-title">name</span>
            <span class="text-h5">{{ content.name }}</span>
          </p>

          <p class="mb-4">
            <span class="sub-title">mail adress</span>
            <span class="text-h5">{{ content.mailadress }}</span>
          </p>

          <p class="mb-4">
            <span class="sub-title">Content</span>
            <span class="text-h5">{{ content.content }}</span>
          </p>
        </v-card-text>

        <v-progress-linear
          indeterminate
          color="yellow darken-2"
          v-show="isSending"
        ></v-progress-linear>
        <v-card-actions class="d-flex justify-space-around">
          <v-btn color="secondary" @click="cancel" class="btn">
            キャンセル
          </v-btn>
          <v-btn color="primary" @click="send" class="btn"> 送信！</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-dialog v-model="isConfirm">
      <v-card>
        <v-card-title>送信完了</v-card-title>
        <v-card-text>
          <p>ご連絡いただきアリガトウゴザイマス。</p>
          <p>できるだけ早くお返事しますので、ショウショウお待ちクダサイ。</p>
        </v-card-text>
        <v-card-text></v-card-text>
        <v-card-actions class="d-flex justify-end">
          <v-btn color="green darken-1" text @click="confirm"> OK! </v-btn>
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
      isSending: false,
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
    async send() {
      this.isSending = true;
      // CORSエラー対策
      const CORS_PROXY = "https://cors-anywhere.herokuapp.com/";
      // Googleフォームのaction属性値
      const GOOGLE_FORM_ACTION =
        "https://docs.google.com/forms/u/0/d/e/1FAIpQLScNaX1t1grG6uIi5qG2pfnpFBf0fGr4S5HtUFESlPiu1xw1Yw/formResponse";
      const params = new FormData();
      params.append("entry.2145197953", this.content.name);
      params.append("entry.663343677", this.content.mailadress);
      params.append("entry.1396251703", this.content.content);
      await this.$axios.$post(CORS_PROXY + GOOGLE_FORM_ACTION, params);
      this.$emit("change", false);
      this.isConfirm = true;
      this.isSending = false;
    },
    confirm() {
      this.isConfirm = false;
      this.$emit("confirm");
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
  padding: 0 0.3em;
  margin-bottom: 0.2em;
  border: 1px solid var(--main-color);
  font-size: 0.8em;
}

.btn {
  width: 46%;
}
</style>
