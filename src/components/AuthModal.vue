<template>
    <Modal @close="$emit('close')">
      <div>
        <h2 v-if="type === 'login'">Авторизация</h2>
        <h2 v-else>Регистрация</h2>
        <form @submit.prevent="submitForm">
          <div>
            <label for="email">Email:</label>
            <input v-model="email" type="email" required />
          </div>
          <div>
            <label for="password">Пароль:</label>
            <input v-model="password" type="password" required />
          </div>
          <button type="submit">{{ type === 'login' ? 'Войти' : 'Зарегистрироваться' }}</button>
        </form>
      </div>
    </Modal>
  </template>
  
  <script>
  import Modal from './Modal.vue';
  export default {
    name: 'AuthModal',
    components: { Modal },
    props: {
      type: String, // 'login' или 'register'
    },
    data() {
      return {
        email: '',
        password: '',
      };
    },
    methods: {
      submitForm() {
        console.log(`Auth type: ${this.type}`, { email: this.email, password: this.password });
        this.$emit('close');
      },
    },
  };
  </script>