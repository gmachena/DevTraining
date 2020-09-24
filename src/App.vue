<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <p>{{ 2 + 1 }}</p>
    <hr />
    <UserForm />
    <hr />
    <Rating :rating="2 + 2" alt="coolItem" />
    <hr />
    <section>
      <h2>User cards</h2>
      <UserCard v-for="(user, i) in users" :key="i" :user="user" />
    </section>
    <hr />
    <section>
      <h2>ID cards</h2>
      <IDCard
        v-for="user in users"
        :key="user.codeName"
        :fullName="user.fullName"
        :codeName="user.codeName"
      />
    </section>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import IDCard from "./components/IDCard.vue";
import Rating from "./components/Rating.vue";
import UserCard from "./components/UserCard.vue";
import UserForm from "./components/UserForm.vue";
import { data } from "./assets/data.js";
import { ref } from "@vue/composition-api";

export default Vue.extend({
  name: "App",
  components: {
    IDCard,
    UserCard,
    Rating,
    UserForm
  },
  setup() {
    const users = ref(data.users);
    return {
      users,
      initialRating: 4
    };
  }
});
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.second {
  background-color: red;
}
</style>
