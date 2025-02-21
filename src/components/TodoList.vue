<template>
  <ul>
    <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" @remove-todo="$emit('remove-todo', todo.id)" />
  </ul>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: { TodoItem },
  props: ["todos"],
  emits: ["remove-todo"],
};
</script>
