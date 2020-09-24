<template>
  <form v-on:submit.prevent="sendForm" class="container">
    <p>
      <label for="codeName">
        Quadri
      </label>
      <input id="codeName" v-model="state.user.codeName" type="text" name="codeName" />
    </p>
    <p>
      <label for="fullName">
        nom / prénom
      </label>
      <input id="fullName" v-model="state.user.fullName" type="text" name="fullName" />
    </p>
    <p>
      <label for="status">
        Statut
      </label>
      <input id="status" v-model="state.user.status" type="text" name="status" />
    </p>
    <p>
      <label for="avatar">
        avatar
      </label>
      <input id="avatar" v-model="state.user.avatar" type="text" name="avatar" />
    </p>
    <p>
      <SubmitButton />
    </p>

  </form>
</template>

<script>
import SubmitButton from "./submitButton.vue";
import { reactive, defineComponent } from "@vue/composition-api";

export default defineComponent({
  components: {
    SubmitButton
  },
  setup(props, context) {
    const user = {
      codeName: "",
      fullName: "",
      status: "",
      avatar: ""
    };
    const state = reactive({
      user
    });
    function sendForm() {
      console.log(state.user);
      context.emit("createUser", state.user);
    }

    return {
      state,
      sendForm
    };
  }
});
</script>

<style scoped>
.container {
  padding: 1em;
  text-align: left;
}
p {
  display: flex;
  flex-direction: row;
  text-align: left;
}
label {
  display: block;
  width: 200px;
}
input {
  width: 200px;
}
</style>
