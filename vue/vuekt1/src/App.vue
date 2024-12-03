<template>
  <main>
    <AddTodo @add="addTodo"></AddTodo>
    <TodoList 
      :todos="todos" 
      @remove="deleteTodo" 
      @change="toggleTodo"
    ></TodoList>
  </main>
</template>

<script>
import AddTodo from './components/AddTodo.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    AddTodo,
    TodoList
  },
  data() {
    return {
      todos: [
        { id: 1, title: 'Have breakfast', completed: true },
        { id: 2, title: 'Clean cucumbers', completed: false },
        { id: 3, title: 'Wash the cat', completed: true }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    toggleTodo(id) {
      this.todos = this.todos.map(todo => 
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
      );
    },
    addTodo(title) {
      this.todos.push({
        id: Date.now(),
        title,
        completed: false
      });
    }
  }
};
</script>

<style scoped>
main {
  padding: 1rem;
}
</style>
