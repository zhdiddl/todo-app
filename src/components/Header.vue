<template>
  <header>
    <h1 class="date">{{ today }}</h1>
    <p class="task-count">{{ todos.length }} tasks</p>
  </header>
</template>

<script>
export default {
  props: ["todos"],
  data() {
    return {
      today: new Date().toLocaleDateString("ko-KR", {
        year: "numeric",
        month: "long",
        day: "numeric",
        weekday: "long",
      }),
    };
  },
};
</script>

<style scoped>
.date {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 5px;
}
.task-count {
  font-size: 14px;
  color: gray;
}
</style>
