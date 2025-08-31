<template lang="">
  <li>
    <h2>
      {{ friends.name }}
    </h2>
    <button @click="toggleDetails">show detail</button>
    <ul v-if="detailsAreVisible">
      <li><strong>phone :</strong> {{ friends.phone }}</li>
      <li><strong>email :</strong> {{ friends.email }}</li>
    </ul>
  </li>
</template>
<script>
export default {
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "manuel",
        name: "manuel lorenz",
        phone: "0123 4567 90",
        email: "manuel@localhost.com",
      },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
  },
};
</script>
<style lang=""></style>
