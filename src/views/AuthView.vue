<template>
    <div class="auth-view">
      <AuthModal type="login" />
    </div>
  </template>
  
  <script>
  import AuthModal from '../components/AuthModal.vue';
  
  export default {
    name: 'AuthView',
    components: { AuthModal },
  };
  </script>
  
  <style scoped>
  .auth-view {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f4f4f4;
  }
  </style>