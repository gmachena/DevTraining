<template>
  <div class="idcard">
    <div class="idcard__avatar"></div>
    <div class="idcard__infos">
      <h2>{{ codeName }}</h2>
      <h4>{{ fullName }}</h4>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    codeName: {
      type: String,
      default: "Waiting quadri"
    },
    fullName: {
      type: String,
      default: "Waiting fullName"
    }
  }
};
</script>

<style>
.idcard {
  display: flex;
  flex-direction: row;
  padding: 1em;
}
.idcard__avatar {
  min-width: 12em;
  background-image: url("https://source.unsplash.com/1600x900/?nature,flower");
  background-size: cover;
  border-radius: 50%;
  height: 12em;
}
.idcard__infos {
  text-align: left;
  margin-left: 1em;
}
</style>
