<template>
  <li>
    <h2>{{ name }} {{ isFavoriteFriend ? "(favorite)" : "" }}</h2>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide details" : "Show details" }}
    </button>
    <button @click="toggleFavorite">Toggle favorite</button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone:</strong>{{ phoneNumber }}</li>
      <li><strong>Email:</strong>{{ emailAddres }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: false,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddres: {
      type: String,
      required: true,
    },
    favorite: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isFavoriteFriend: this.favorite,
      detailsAreVisible: false,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.isFavoriteFriend = !this.isFavoriteFriend;
    },
  },
};
</script>