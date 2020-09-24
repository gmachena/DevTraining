<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <p>{{ 2 + 1 }}</p>
    <hr />
    <UserForm v-on:createUser="createUser" />
    <hr />
    <ADNButton @send="addCar" label="Ajouter une voiture" />
    <hr />
    <Rating :rating="2 + 2" alt="coolItem" />
    <hr />
    <section>
      <h2>User cards</h2>
      <UserCard v-for="(user, i) in state.users" :key="i" :user="user" />
    </section>
    <hr />
    <section>
      <h2>ID cards</h2>
      <!-- <IDCard
        v-for="user in users"
        :key="user.codeName"
        :fullName="user.fullName"
        :codeName="user.codeName"
      /> -->
    </section>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
//import IDCard from "./components/IDCard.vue";
import ADNButton from "./components/ADNButton.vue";
import Rating from "./components/Rating.vue";
import UserCard from "./components/UserCard.vue";
import UserForm from "./components/UserForm.vue";
import { data } from "./assets/data.js";
import { reactive, /*ref, toRefs*/ } from "@vue/composition-api";

interface User {
  codeName: string;
  fullName: string;
  status: string;
  avatar: string;
  skills : {
    label: string,
    rating: string
  }[]
}

export default Vue.extend({
  name: "App",
  components: {
    //IDCard,
    UserCard,
    Rating,
    UserForm,
    ADNButton
  },
  setup() {
    //const users = ref(data.users); // ref = donnée reactive
    const state = reactive({
      users: data.users
    });
    function createUser(user: any) {
      state.users.push(user);
    }
    function addCar() {
      // change la reactive
      state.users = data.users.map(user => {
        user.fullName = user.fullName + " 🚔";
        return user;
      });
      // change la ref
      // users.value = data.users.map(user => {
      //   user.fullName = user.fullName + " 🚔";
      //   return user;
      // });
    }
    return {
      data,
      state, // soit on expose le state reatif (reactive)
      //...toRefs(state), // soit on expose les refs issues du state (reactive)
      // users, // soit un expose une ref directement
      initialRating: 4,
      addCar,
      createUser
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
