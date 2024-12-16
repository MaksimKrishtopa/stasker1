<template>
  <div id="app">
    <Header @show-modal="showModal" />
    <TaskForm @task-added="addTask" />
    <TaskBoard :tasks="tasks" />
    <AuthModal v-if="showAuth" :type="modalType" @close="showAuth = false" />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import TaskForm from './components/TaskForm.vue';
import TaskBoard from './components/TaskBoard.vue';
import AuthModal from './components/AuthModal.vue';

export default {
  components: { Header, TaskForm, TaskBoard, AuthModal },
  data() {
    return {
      tasks: [],
      showAuth: false,
      modalType: ''
    };
  },
  methods: {
    showModal(type) {
      this.modalType = type;
      this.showAuth = true;
    },
    addTask(task) {
      this.tasks.push({ ...task, id: Date.now() });
    }
  }
};
</script>

<style>
@import './assets/css/style.css';
</style>