<!-- TEMPLATE ### default -->
<template>
  {{ `Hi, ${first_name}` }}<br />

  <button>Logout</button>

  <!-- Aufruf einer Komponente -->
  <br /><br />
  <h3>TodoList</h3>
  <TodoList />
  <br /><br />
</template>
<!-- TEMPLATE ENDE -->

<!-- SCRIPT / Funktionalität -->
<script>
/*
 * IMPORT
 *
 */
import TodoList from "./components/TodoList";

/*
 * EXPORT
 *
 */
export default {
  name: "App",
  data: () => ({
    first_name: "Torsten",
  }),
  components: {
    TodoList,
  },
};
</script>

<!-- STYLE -->
<style>
* {
  margin: 0;
  padding: 0;
}
ul {
  list-style: none;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 60px;
}
</style>
