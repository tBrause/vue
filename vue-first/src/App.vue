<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <hr />
  {{ `Hi, ${first_name}` }}<br />
  {{ fullName }}

  <!--
  {{ age > 18 ? "voll" : "nicht voll" }}
  -->

  <div class="age">
    <span v-if="age < 18">nicht voll</span>
    <span v-else-if="age == 18">voll</span>
    <span v-else>Ü18</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    first_name: "Torsten",
    last_name: "Brause",
    age: 51,
  }),
  computed: {
    fullName() {
      return `${this.first_name} ${this.last_name}`;
    },
  },
};
</script>

<style>
.age {
  border: 1px solid #666;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
