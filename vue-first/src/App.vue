<!-- TEMPLATE ### default -->
<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <hr />
  {{ `Hi, ${first_name}` }}<br />
  {{ fullName }}

  <!--
  {{ age > 18 ? "voll" : "nicht voll" }}
  -->

  <!-- v-if (nur true wird gerendert) -->
  <div class="age">
    <span v-if="age < 18">nicht voll</span>
    <span v-else-if="age == 18">voll</span>
    <span v-else>Ü18</span>
  </div>

  <!-- v-show (wird gerendert (display: none)) -->
  <div v-show="first_name == 'Torste'">hallo T</div>

  <!-- Array CITIES auslesen mit internem INDEX -->
  <ul>
    <li v-for="(city, index) in cities" v-bind:key="city.id">
      {{ index }} {{ city.name }}
    </li>
  </ul>

  <!-- Array TODOS auslesen mit internem INDEX -->
  <!--<ul>
    <li
      v-for="(todo, index) in todos"
      v-bind:key="todo.id"
      v-bind:class="{ finishedTask: todo.finished }"
    >
      <input type="checkbox" v-bind:checked="todo.finished" />

      <a v-bind:href="'?id=' + todo.id">zeigen</a>
      {{ index }} {{ todo.name }}
    </li>
  </ul>-->

  <!-- Aufruf einer Komponente -->
  <br /><br />
  <h3>TodoList</h3>
  <TodoList />
  <br /><br />
  <button v-on:click="test">Test</button>
  <button @click="test">Test2</button>

  <!-- Anzahl der Elemente im Array -->
  <p>Anzahl Städte: {{ cities.length }}</p>

  <!-- Forschleife mit n -->
  <p v-for="n in cities.length" v-bind:key="n">{{ n }}</p>
</template>

<!-- TEMPLATE ENDE -->

<!-- SCRIPT / Funktionalität -->
<script>
// IMPORT
import TodoList from "./components/TodoList";

// EXPORT
export default {
  name: "App",
  data: () => ({
    first_name: "Torsten",
    last_name: "Brause",
    age: 51,
    cities: [
      { id: 1, name: "Berlin" },
      { id: 2, name: "Dresden" },
      { id: 3, name: "Gera" },
      { id: 4, name: "Prag" },
    ],
  }),
  computed: {
    fullName() {
      return `${this.first_name} ${this.last_name}`;
    },
  },
  methods: {
    test() {
      alert("Hi");
    },
  },
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
.age {
  border: 1px solid #666;
  padding: 1em;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}

.finishedTask {
  background-color: #ccc;
}
</style>
