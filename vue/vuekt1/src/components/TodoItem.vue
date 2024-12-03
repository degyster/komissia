<template>
  <article 
    class="todo-item" 
    @click="handleRemove" 
    @dblclick="handleChange" 
    :class="{ completed: completed }"
  >
    <h2>{{ title }}</h2>
  </article>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    title: String,
    completed: Boolean,
    id: [String, Number]
  },
  emits: ['change', 'remove'],
  methods: {
    handleChange() {
      this.$emit('change', this.id);
    },
    handleRemove() {
      this.$emit('remove', this.id);
    }
  }
};
</script>

<style scoped>
.completed {
  background-color: green;
}
.todo-item {
  background-color: red;
}
</style>
