<template lang="">
  <li>
    <h2>{{ name }} {{ friendIsFavorite ? "(Favorite)" : "" }}</h2>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "show detail" }}
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>phone :</strong> {{ phoneNumber }}</li>
      <li><strong>email :</strong> {{ emailAddress }}</li>
    </ul>
  </li>
</template>
<script>
export default {
  // props: ["name", "phoneNumber", "emailAddress", "isFavorite"],
  props: {
    id: {
      type: string,
      required: true,
    },
    name: string,
    phoneNumber: string,
    emailAddress: string,
    isFavorite: {
      type: boolean,
      required: false,
      default: 0,
    },
  },
  emits: {
    "toggle-favorite" : function(id){
      if(id){
        return true;
      }
      else{
        console.log('id is missing');

        return false
      }
    }
  }
  data() {
    return {
      detailsAreVisible: false,
      friendIsFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>
<style lang=""></style>
