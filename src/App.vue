<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <p>{{ 2 + 1 }}</p>
    <Rating :rating="2" alt="coolItem" />
    <IDCard fullName="Armando Maradona" codeName="ARMA" />
    <IDCard fullName="Armando Maradona" codeName="ARMA" />
    <IDCard fullName="Armando Maradona" codeName="ARMA" />
    <IDCard fullName="Armando Maradona" codeName="ARMA" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import IDCard from "./components/IDCard.vue";
import Rating from "./components/Rating.vue";

export default Vue.extend({
  name: "App",
  components: {
    IDCard,
    Rating
  },
  setup() {
    return {
      initialRating: 4
    };
  }
});
</script>

<style>
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
