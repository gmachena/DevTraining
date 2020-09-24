<template>
  <div class="user-card">
    <div class="user-card__avatar"></div>
    <div class="user-card__infos">
      <h2>{{ codeName }}</h2>
      <h4>{{ fullName }}</h4>
    </div>
  </div>
</template>

<script>
import { computed } from "@vue/composition-api";
export default {
  props: {
    user: Object
  },
  setup(props) {
    const fullNameWithCar = computed(() => props.user?.fullName + " 🚔");

    return {
      codeName: props.user?.codeName,
      fullName: fullNameWithCar
    };
  }
};
</script>

<style>
.user-card {
  display: flex;
  flex-direction: row;
  padding: 1em;
}
.user-card__avatar {
  min-width: 12em;
  background-image: url("https://source.unsplash.com/1600x900/?nature,flower");
  background-size: cover;
  border-radius: 50%;
  height: 12em;
}
.user-card__infos {
  text-align: left;
  margin-left: 1em;
}
</style>
