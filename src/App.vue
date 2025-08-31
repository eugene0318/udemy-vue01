<template lang="">
  <section>
    <hreader><h2>My Freinds</h2></hreader>
    <new-freind @add-contact="addContact"></new-freind>
    <ul>
      <friend-contact
        v-for="friend in Freinds"
        :key="Freind.id"
        :id="friend.id"
        :name="friend.name"
        :phoneNumber="friend.phone"
        :emailAddress="friend.email"
        :is-favorite="friend.isFavorite"
        @toggle-favorite="toggleFavoriteStatus"
      ></friend-contact>
    </ul>
  </section>
</template>
<script>
export default {
  data() {
    return {
      friends: [
        {
          id: "manuel",
          name: "manuel lorenz",
          phone: "0123 4567 90",
          email: "manuel@localhost.com",
          isFavorite: true,
        },
        {
          id: "julie",
          name: "julie jones",
          phone: "1234 5678 91",
          email: "julie@localhost.com",
          isFavorite: false,
        },
      ],
    };
  },
  methods: {
    toggleFavoriteStatus(friendId) {
      const identifiedFriend = this.friends.find(
        friend => friend.id === friendId
      );
      identifiedFriend.isFavorite = !identifiedFriend.isFavorite;
    },
    addContact(name, phone, email) {
      const NewFriendContact = {
        id: new Data().toISOString(),
        name: name,
        phone: phone,
        email: email,
        isFavorite: false,
      };
      this.friends.push(NewFriendContact);
    },
  },
};
</script>
<style lang=""></style>
