<template>
  <section class="add-todo">
    <input 
      type="text" 
      @keydown.enter="addTodo" 
      v-model="text" 
      placeholder="Enter a new todo"
    />
  </section>
</template>

<script>
export default {
  name: 'AddTodo',
  data() {
    return {
      text: ''
    };
  },
  methods: {
    addTodo() {
      console.log(this.text);
      this.$emit('add', this.text);
      this.text = '';
    }
  }
};
</script>

<style scoped>
.add-todo input {
  width: 100%;
  padding: 8px;
  font-size: 1rem;
}
</style>
