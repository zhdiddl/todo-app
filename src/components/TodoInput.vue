<template>
  <div>
    <input v-model="newTodo" placeholder="할 일을 입력하세요" @keyup.enter="addTodo" />
    <button @click="addTodo">추가</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: "",
    };
  },
  emits: ["add-todo"],
  methods: {
    addTodo() {
      if (this.newTodo.trim() === "") return;
      this.$emit("add-todo", this.newTodo);
      this.newTodo = "";
    },
  },
};
</script>

<style scoped>
input {
  padding: 8px;
  margin-right: 10px;
}
button {
  padding: 8px;
  background-color: green;
  color: white;
  border: none;
  cursor: pointer;
}
</style>
