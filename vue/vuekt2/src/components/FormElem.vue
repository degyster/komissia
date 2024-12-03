<template>
  <section class="form-container">
    <InputElem 
      @changeProp="handleChange" 
      key_name="name" 
      type="text" 
      placeholder="Name"
    />
    <InputElem 
      @changeProp="handleChange" 
      key_name="phone" 
      type="tel" 
      placeholder="Phone"
    />
    <InputElem 
      @changeProp="handleChange" 
      key_name="email" 
      type="email" 
      placeholder="Email"
    />
    <InputElem 
      @changeProp="handleChange" 
      key_name="date" 
      type="date" 
      placeholder="Date"
    />
  </section>
</template>

<script>
import InputElem from '@/UI/InputElem.vue';

export default {
  name: 'FormElem',
  props: {
    form: {
      type: Object,
      required: true
    }
  },
  emits: ['changeProp'],
  components: {
    InputElem
  },
  methods: {
    handleChange(prop, value) {
      this.$emit('changeProp', prop, value);
    }
  }
};
</script>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  gap: 15px;
  max-width: 400px;
  margin: 0 auto;
}
</style>
