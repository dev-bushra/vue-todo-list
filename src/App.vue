<template>
  <div id="app">
    <div class="container py-4">
      <AddTodo />
      <FilterTodo />
      <todos />
    </div>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
import FilterTodo from "./components/FilterTodo";

export default {
  name: "App",
  components: {
    Todos,
    AddTodo,
    FilterTodo
  }
};
</script>

<style></style>
