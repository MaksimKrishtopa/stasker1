<template>
    <div class="column">
      <h2>{{ title }}</h2>
      <div class="tasks">
        <TaskCard v-for="task in tasks" :key="task.id" :task="task" />
      </div>
    </div>
  </template>
  
  <script>
  import TaskCard from './TaskCard.vue';
  
  export default {
    components: { TaskCard },
    props: {
      title: String,
      tasks: Array
    }
  };
  </script>
  
  <style scoped>
  .column {
    width: 45%;
    background-color: white;
    padding: 10px;
    border-radius: 8px;
  }
  </style>