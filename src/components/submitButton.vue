<template>
  <div>
    <button class="color-button" type="submit" v-on:click="changeColor">
      soumettre
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    changeColor() {
      console.log("coucou ici")
    }
  }
};
</script>

<style>
.color-button {
  color: red;
}
</style>
