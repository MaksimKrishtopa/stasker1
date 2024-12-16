<template>
    <div class="task-form">
      <input v-model="taskName" type="text" placeholder="Название задачи" required />
      <textarea v-model="taskDescription" placeholder="Описание задачи" required></textarea>
      <input v-model="startTime" type="datetime-local" required />
      <input v-model="endTime" type="datetime-local" required />
      <button @click="addTask">Добавить задачу</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        taskName: '',
        taskDescription: '',
        startTime: '',
        endTime: ''
      };
    },
    methods: {
      addTask() {
        const newTask = {
          name: this.taskName,
          description: this.taskDescription,
          startTime: this.startTime,
          endTime: this.endTime,
          status: 'planned'
        };
        this.$emit('task-added', newTask);
        this.resetForm();
      },
      resetForm() {
        this.taskName = '';
        this.taskDescription = '';
        this.startTime = '';
        this.endTime = '';
      }
    }
  };
  </script>
  
  <style scoped>
  @import '../assets/css/style.css';
  </style>