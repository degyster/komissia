<template>
  <input 
    :placeholder="placeholder" 
    :type="type" 
    class="input-element" 
    @input="handleInput" 
  />
</template>

<script>
export default {
  name: 'InputElem',
  props: {
    type: {
      type: String,
      required: true
    },
    placeholder: {
      type: String,
      required: true
    },
    key_name: {
      type: String,
      required: true
    }
  },
  emits: ['changeProp'],
  methods: {
    handleInput(event) {
      this.$emit('changeProp', this.key_name, event.target.value);
    }
  }
};
</script>

<style scoped>
.input-element {
  padding: 5px 20px;
  border-radius: 15px;
  outline: none;
  border: 1px solid black;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

.input-element:focus {
  border-color: lightblue;
  box-shadow: 0 0 5px lightblue;
}
</style>
