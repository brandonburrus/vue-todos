<template>
  <form class="col-12 col-sm-10 col-md-8 cl-lg-6" @submit.prevent="addTodo()">
    <input
      v-model="newTodo"
      type="text"
      class="form-control"
      placeholder="Create a new to-do..."
    />
  </form>
</template>

<script>
export default {
  data() {
    return {
      newTodo: ""
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.length > 0) {
        this.$emit("on-new-todo", this.newTodo);
      }
      this.newTodo = "";
    }
  }
};
</script>

<style lang="scss" scoped></style>
