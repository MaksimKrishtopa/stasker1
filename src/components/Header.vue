<template>
    <header class="header">
      <h1>Планировщик задач</h1>
      <div class="auth-buttons">
        <button v-if="!isAuthenticated" @click="showLogin">Авторизация</button>
        <button v-if="!isAuthenticated" @click="showRegister">Регистрация</button>
        <button v-if="isAuthenticated" @click="logout">Выход</button>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isAuthenticated: false
      };
    },
    methods: {
      showLogin() {
        this.$emit('show-modal', 'login');
      },
      showRegister() {
        this.$emit('show-modal', 'register');
      },
      logout() {
        this.isAuthenticated = false;
      }
    }
  };
  </script>
  
  <style scoped>
  @import '../assets/css/style.css';
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    background-color: #f9f9f9;
  }
  .auth-buttons button {
    margin-left: 10px;
  }
  </style>