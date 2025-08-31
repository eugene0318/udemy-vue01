<template lang="">
  <form @submit.prevent="submitData">
    <div>
      <label>name</label>
      <input type="text" v-model="enteredName" />
    </div>
    <div>
      <label>phone</label>
      <input type="tel" v-model="enteredPhone" />
    </div>
    <div>
      <label>e-mail</label>
      <input type="email" v-model="enteredEmail" />
    </div>
    <div>
      <button>add contact</button>
    </div>
  </form>
</template>
<script>
export default {
  emits: ["add-contact"],
  data() {
    return {
      enteredName: "",
      enteredPhone: "",
      enteredEmail: "",
    };
  },
  method: {
    submitData() {
      this.$emit(
        "add-contact",
        this.enteredName,
        this.enteredPhone,
        this.enteredEmail
      );
    },
  },
};
</script>
<style lang=""></style>
