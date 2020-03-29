<template>
  <li class="d-flex align-items-center list-group-item">
    <button
      class="btn border-0 flex-grow-1 text-left shadow-none"
      :class="{ completed }"
      @click="$emit('on-toggle')"
    >
      {{ description }}
    </button>
    <button @click="$emit('on-delete')" class="btn btn-outline-danger border-0 float-right">
      <span class="fa fa-trash"></span>
    </button>
  </li>
</template>

<script>
export default {
  props: {
    description: String,
    completed: Boolean,
  },
};
</script>

<style lang="scss" scoped>
.completed {
  text-decoration: line-through;
}
</style>
