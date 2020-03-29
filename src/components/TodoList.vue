<template>
  <div class="container">
    <div class="row">
      <div class="col-12 py-5">
        <h1>{{ listName }}</h1>
      </div>
    </div>
    <div class="row">
      <div class="col-12 col-sm-10 col-lg-6">
        <ul class="list-group">
          <todo
            v-for="(todo, index) in todos"
            :key="index"
            :description="todo.description"
            :completed="todo.completed"
            @on-toggle="toggleTodo(todo)"
            @on-delete="deleteTodo(todo)"
          />
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import Todo from "./Todo.vue";
export default {
  props: {
    listName: String,
  },
  data() {
    return {
      todos: [
        { description: "Do the dishes", completed: false },
        { description: "Take out the trash", completed: false },
        { description: "Finish doing laundry", completed: false },
      ],
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
    toggleTodo(todo) {
      todo.completed = !todo.completed;
    },
    deleteTodo(deletedTodo) {
      this.todos = this.todos.filter(todo => todo !== deletedTodo);
    },
  },
  components: { Todo },
};
</script>

<style scoped lang="scss"></style>
