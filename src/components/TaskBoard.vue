<template>
    <div class="board">
      <TaskColumn title="Запланированные" :tasks="plannedTasks" />
      <TaskColumn title="Завершенные" :tasks="completedTasks" />
    </div>
  </template>
  
  <script>
  import TaskColumn from './TaskColumn.vue';
  
  export default {
    components: { TaskColumn },
    props: {
      tasks: Array
    },
    computed: {
      plannedTasks() {
        return this.tasks.filter(task => task.status === 'planned');
      },
      completedTasks() {
        return this.tasks.filter(task => task.status === 'completed');
      }
    }
  };
  </script>
  
  <style scoped>
  .board {
    display: flex;
    justify-content: space-around;
    padding: 20px;
  }
  </style>