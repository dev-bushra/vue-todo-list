<template>
  <section>
    <h3 class="mb-4">
      Todos
      <span class="right"
        >Double click to mark as completed
        <span class="teal px-3 white-text"></span> Completed
        <span class="grey darken-3 px-3 white-text"></span> Not Completed</span
      >
    </h3>

    <div class="todos">
      <div
        @dblclick="onDclick(todo)"
        v-for="todo in allTodos"
        :key="todo.id"
        :class="
          `todo ${
            todo.completed ? 'teal lighten-1' : 'grey darken-3'
          } z-depth-1`
        "
      >
        <h4>{{ todo.title }}</h4>
        <i @click="deleteTodo(todo.id)" class="material-icons text-white"
          >delete</i
        >
      </div>
    </div>
  </section>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "Todos",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDclick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      };
      this.updateTodo(updTodo);
    }
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  }
};
</script>

<style scoped>
section {
  padding: 1rem 0;
}
.todo {
  padding: 1rem;
  min-height: 100px;
  text-align: center;
  position: relative;
}
.todo h4 {
  margin: 0;
  color: #fff;
  text-transform: capitalize;
}
.todos {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
}
.todo i {
  position: absolute;
  bottom: 0.5rem;
  right: 0.5rem;
  cursor: pointer;
}
h3 span {
  font-size: 16px;
}
span.right {
  width: 50%;
  display: flex;
  justify-content: space-between;
}
</style>
