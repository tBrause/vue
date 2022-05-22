<!-- TEMPLATE ### Alle Items -->
<template>
  <!-- Array TODOS auslesen mit internem INDEX -->
  <ul>
    <TodoListItem v-for="todo in todos" :key="todo.id" :item="todo" />
  </ul>
</template>
<!-- TEMPLATE ENDE -->

<!-- SCRIPT -->
<script>
import TodoListItem from "./TodoListItem";

export default {
  name: "TodoList",
  data: () => ({
    todos: [
      { id: 1, finished: false, name: "Vue.js lernen" },
      { id: 2, finished: false, name: "Code Beispiel üben" },
      { id: 3, finished: false, name: "Git commit" },
      { id: 4, finished: true, name: "weiteres Todo" },
    ],
  }),
  components: {
    TodoListItem,
  },
};
</script>
<!-- SCRIPT ENDE -->

<!-- STYLE -->
<style></style>
<!-- STYLE ENDE -->
