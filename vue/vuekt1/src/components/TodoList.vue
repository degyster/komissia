<template>
  <section>
    <div v-for="todo in todos" :key="todo.id" class="todo-container">
      <TodoItem 
        @remove="handleRemove" 
        @change="handleChange" 
        :id="todo.id" 
        :title="todo.title" 
        :completed="todo.completed" 
      />
    </div>
  </section>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  name: 'TodoList',
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  emits: ['change', 'remove'],
  methods: {
    handleChange(id) {
      this.$emit('change', id);
    },
    handleRemove(id) {
      this.$emit('remove', id);
    }
  },
  components: {
    TodoItem,
  },
};
</script>

<style scoped>
.todo-container {
  margin-bottom: 10px;
}
</style>
