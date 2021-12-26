<!-- @format -->

<template>
  <div class="home">
    <h1>todos</h1>
    <ul>
      <li v-for="todo in todos" :key="todo.id">{{ todo.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
const baseUrl = `http://localhost:3000/todos`;
export default {
  name: "Home",
  data() {
    return {
      todos: " ",
    };
  },
  mounted() {
    axios.get(baseUrl).then((response) => (this.todos = response.data));
  },
};
</script>
