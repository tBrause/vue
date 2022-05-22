<!-- TEMPLATE ### Ein Item -->
<template>
  <li :class="{ finishedTask: item.finished }">
    <input type="checkbox" v-bind:checked="item.finished" />
    <a v-bind:href="'?id=' + item.id">zeigen</a>
    {{ item.name }}
  </li>
</template>
<!-- TEMPLATE ENDE -->

<!-- SCRIPT -->
<script>
export default {
  name: "TodoListItem",
  data: () => ({
    todos: [
      { id: 1, finished: false, name: "Vue.js lernen" },
      { id: 2, finished: false, name: "Code Beispiel üben" },
      { id: 3, finished: false, name: "Git commit" },
      { id: 4, finished: true, name: "weiteres Todo" },
    ],
  }),
  props: ["item"],
};
</script>
<!-- SCRIPT ENDE -->
