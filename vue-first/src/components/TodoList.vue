<!-- TEMPLATE ### TodoList -->
<template>
  <ul>
    <TodoListItem
      v-for="todo in todos"
      :key="todo.id"
      :item="todo"
      @toogle="toogleListItem"
    />
  </ul>
</template>
<!-- TEMPLATE ENDE -->

<!-- SCRIPT -->
<script>
/*
 * IMPORT
 *
 */
import TodoListItem from "./TodoListItem";

/*
 * EXPORT
 *
 */
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
  methods: {
    toogleListItem(el) {
      console.log(el.name);
      el.finished = !el.finished;
    },
  },
};
</script>
<!-- SCRIPT ENDE -->

<!-- STYLE -->
<style scoped></style>
<!-- STYLE ENDE -->
