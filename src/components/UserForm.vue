<template>
  <form @submit="sendForm" class="container">
    <p>
      <label for="codeName">
        Quadri
      </label>
      <input id="codeName" v-model="codeName" type="text" name="codeName" />
    </p>
    <p>
      <label for="fullName">
        nom / prénom
      </label>
      <input id="fullName" v-model="fullName" type="text" name="fullName" />
    </p>
    <p>
      <label for="status">
        Statut
      </label>
      <input id="status" v-model="status" type="text" name="status" />
    </p>
    <p>
      <label for="avatar">
        avatar
      </label>
      <input id="avatar" v-model="avatar" type="text" name="avatar" />
    </p>
    <p>
      <label for="fullName">
        nom / prénom
      </label>
      <input id="fullName" v-model="fullName" type="text" name="fullName" />
    </p>
  </form>
</template>

<script>
export default {};
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
