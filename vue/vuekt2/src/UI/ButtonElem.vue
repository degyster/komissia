<template>
  <button @click="$emit('submit')" class="button-element">{{ title }}</button>
</template>

<script>
export default {
  name: 'ButtonElem',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  emits: ['submit']
};
</script>

<style scoped>
.button-element {
  padding: 5px 30px;
  border-radius: 15px;
  background-color: plum;
  border: 1px solid black;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.button-element:hover {
  background-color: lightblue;
}
</style>
