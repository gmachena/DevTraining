<template>
  <button type="button" @click="addCar">Ajouter une voiture</button>
</template>

<script>
export default {
  setup(props, context) {
    const addCar = () => {
      console.log("COUCOU");
      context.emit("addParentCar");
    };
    return {
      addCar
    };
  }
};
</script>

<style scoped>
button {
  outline: none;
  padding: 1em;
  border: none;
  background-color: #41b883;
  color: #fafafa;
  font-family: "Century Gothic";
  font-weight: 700;
  cursor: pointer;
}
</style>
