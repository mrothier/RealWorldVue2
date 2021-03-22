<template>
  <div>
    <h1>Create an Event, {{ user.name }}</h1>
    <p>This event was created by {{ user.id }}</p>
    <p>{{ getEventById(1) }}</p>
    <p>There are {{ catLength }} categories</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
  </div>
</template>

<script>
import { mapState, mapGetters } from "vuex";

export default {
  computed: {
    getEvent() {
      return this.$store.getters.getEventbyId;
    },
    catLength() {
      return this.$store.getters.catLength;
    },
    ...mapGetters(["getEventById"]),
    ...mapState(["user", "categories"])
  }
};
</script>

<style lang="scss" scoped></style>
