<template>
  <section>
    <h3 class="">Add Todo</h3>
    <div class="add border border-1 px-4">
      <form @submit="onSubmit">
        <div class="input-field">
          <input id="title" type="text" class="validate" v-model="title" />
          <label for="title">Title</label>
        </div>
        <button
          type="submit"
          class="waves-effect waves-light btn btn-block teal lighten-1 z-depth-1 rounded-0 text-white"
        >
          Add
        </button>
      </form>
    </div>
  </section>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
      this.title = "";
    }
  }
};
</script>

<style scoped>
.btn {
  width: 18%;
  align-self: center;
}
.input-field {
  width: 80%;
  margin-right: 2%;
}
form {
  display: flex;
}
</style>
