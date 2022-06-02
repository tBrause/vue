<!-- TEMPLATE ### TodoListItem -->
<template>
  <li :class="{ finishedTask: item.finished }">
    <a v-bind:href="'?id=' + item.id">zeigen</a>
    <input type="checkbox" :checked="item.finished" />
    <button @click="toogleItem">toogle</button>
    {{ item.name }}
  </li>
</template>
<!-- TEMPLATE ENDE -->

<!-- SCRIPT -->
<script>
// EXPORT
export default {
  name: "TodoListItem",
  props: ["item"],
  methods: {
    toogleItem() {
      this.$emit("toogle", this.item);
    },
  },
};
</script>
<!-- SCRIPT ENDE -->

<!-- STYLE -->
<style scoped>
button {
  color: green;
}
.finishedTask {
  background-color: #ccc;
}
</style>
<!-- STYLE ENDE -->
