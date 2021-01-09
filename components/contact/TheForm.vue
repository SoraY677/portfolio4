<template>
  <v-form class="pa-5 pa-sm-10" ref="form">
    <v-text-field
      label="name"
      class="input-block mb-5"
      :rules="regName"
      v-model="name"
    ></v-text-field>
    <v-text-field
      label="mail adress"
      class="input-block mb-5"
      :rules="regMailadress"
      v-model="mailadress"
    ></v-text-field>
    <v-textarea
      autocomplete="email"
      label="content"
      class="input-block mb-4"
      :rules="regContent"
      v-model="content"
    ></v-textarea>
    <div class="d-flex justify-center button-container">
      <v-btn type="button" class="pa-10 text-sm-h1 text-h3" @click="openModal">
        submit
        <img src="/rocket.svg" height="18" width="18" alt="ロケットの画像" />
      </v-btn>
    </div>
    <confirm-modal
      :content="{
        name: name,
        mailadress: mailadress,
        content: content,
      }"
      :isOpen="isConfirmOpen"
      @change="changeConfirmModal"
      @confirm="reset"
    ></confirm-modal>
  </v-form>
</template>

<script>
import ConfirmModal from "@/components/contact/TheFormConfirmModal.vue";
export default {
  data() {
    return {
      name: "",
      mailadress: "",
      content: "",
      isConfirmOpen: false,
      regName: [(value) => !!value || "Required."],
      regMailadress: [
        (value) => !!value || "Required.",
        (value) => {
          const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
          return pattern.test(value) || "Invalid e-mail.";
        },
      ],
      regContent: [(value) => !!value || "Required."],
    };
  },
  methods: {
    reset() {
      this.$refs.form.reset();
    },
    openModal() {
      const validate = this.$refs.form.validate();
      if (validate == true) this.isConfirmOpen = true;
    },
    changeConfirmModal(isOpen) {
      this.isConfirmOpen = isOpen;
    },
  },

  components: {
    ConfirmModal,
  },
};
</script>

<style scoped>
form {
  background-color: var(--main-color);
}
.input-block {
  padding: 0.8em 2em 0.2em 2em;
  background-color: var(--bg-color);
  border-radius: 3em;
}

.button-container {
  font-size: 0.6em;
}

img {
  height: 1.4em;
  width: 1.4em;
}
</style>
