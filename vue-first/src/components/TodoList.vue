<!-- TEMPLATE ### TodoList -->
<template>
  <ul>
    <TodoListItem v-for="todo in todos" :key="todo.id" :item="todo" />
  </ul>
</template>
<!-- TEMPLATE ENDE -->

<!-- SCRIPT -->
<script>
// IMPORT
import TodoListItem from "./TodoListItem";

// EXPORT
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
