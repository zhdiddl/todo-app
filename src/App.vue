<template>
  <div>
    <Header :todos="todos" />
    <TodoInput @add-todo="addTodo" />
    <TodoList :todos="todos" @remove-todo="removeTodo" />
    <Footer />
  </div>
</template>

<script>
import { ref } from "vue";
import Header from "./components/Header.vue";
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";
import Footer from "./components/Footer.vue";

export default {
  components: { Header, TodoInput, TodoList, Footer },
  setup() {
    const todos = ref([
      { id: 1, text: "스트레칭하기 :)", completed: false },
      { id: 2, text: "물 마시기!", completed: false },
    ]);

    const addTodo = (text) => {
      todos.value.push({ id: Date.now(), text, completed: false });
    };

    const removeTodo = (id) => {
      todos.value = todos.value.filter((todo) => todo.id !== id);
    };

    return { todos, addTodo, removeTodo };
  },
};
</script>

<style>
body {
  font-family: "Noto Sans KR", sans-serif; 
  max-width: 400px;
  margin: auto;
  padding: 20px;
}
ul {
  list-style: none;
  padding: 0;
}
</style>
