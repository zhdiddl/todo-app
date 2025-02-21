<template>
  <li>
    <input type="checkbox" v-model="todo.completed" />
    <span :class="{ completed: todo.completed }">{{ todo.text }}</span>
    <button @click="$emit('remove-todo', todo.id)">삭제</button>
  </li>
</template>

<script>
export default {
  props: ["todo"],
  emits: ["remove-todo"],
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
  color: gray;
}
button {
  margin-left: 10px;
  padding: 8px;
  background-color: red;
  color: white;
  border: none;
  cursor: pointer;
}
</style>
