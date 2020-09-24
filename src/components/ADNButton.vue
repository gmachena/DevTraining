<template>
  <button type="button" @click="send">{{ label }}</button>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: "send"
    }
  },
  setup(props, context) {
    const send = () => {
      context.emit("send");
    };
    return {
      send
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
