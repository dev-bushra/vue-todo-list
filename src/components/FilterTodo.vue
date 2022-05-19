<template>
  <section class="pt-4">
    <h3>Filter Todos :</h3>
    <div class="input-field col s12">
      <select v-model="limit" @change="filterTodos(limit)" class="border">
        <option value="200" selected>200</option>
        <option value="100">100</option>
        <option value="20">20</option>
        <option value="10">10</option>
        <option value="5">5</option>
      </select>
    </div>
  </section>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "FilterTodo",
  data() {
    return {
      limit: 200
    };
  },
  methods: mapActions(["filterTodos"])
};
</script>

<style>
select {
  display: block;
}
</style>
