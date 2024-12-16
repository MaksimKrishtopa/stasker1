<template>
    <div class="task">
      <h3>{{ task.name }}</h3>
      <p>{{ task.description }}</p>
      <div>
        <button @click="$emit('edit-task', task)">Редактировать</button>
        <button @click="$emit('delete-task', task.id)">Удалить</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      task: Object
    }
  };
  </script>
  
  <style scoped>
  .task {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px 0;
  }
  button {
    margin-right: 5px;
  }
  </style>