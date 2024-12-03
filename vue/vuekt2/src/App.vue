<template>
  <main class="app-container">
    <FormElem @changeProp="updateForm" :form="form" />
    <ButtonElem @submit="handleSubmit" :title="'Submit'" />
  </main>
</template>

<script>
import ButtonElem from './UI/ButtonElem.vue';
import FormElem from './components/FormElem.vue';

export default {
  name: 'App',
  components: {
    ButtonElem,
    FormElem
  },
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        date: ''
      }
    };
  },
  methods: {
    handleSubmit() {
      console.log({ ...this.form });
    },
    updateForm(prop, value) {
      this.form[prop] = value;
    }
  }
};
</script>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 25px;
  padding: 20px;
  max-width: 600px;
  margin: 0 auto;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  background-color: #f9f9f9;
}
</style>
