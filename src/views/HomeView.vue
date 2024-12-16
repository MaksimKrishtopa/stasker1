<template>
  <div>
    <Header @show-modal="showAuthModal" />
    <TaskForm @task-added="addTask" />
    <TaskBoard :tasks="tasks" />
    <AuthModal v-if="showModal" :type="authType" @close="showModal = false" />
  </div>
</template>

<script>
import Header from '../components/Header.vue';
import TaskForm from '../components/TaskForm.vue';
import TaskBoard from '../components/TaskBoard.vue';
import AuthModal from '../components/AuthModal.vue';

export default {
  name: 'HomeView',
  components: { Header, TaskForm, TaskBoard, AuthModal },
  data() {
    return {
      tasks: [],
      showModal: false,
      authType: '',
    };
  },
  methods: {
    showAuthModal(type) {
      this.authType = type;
      this.showModal = true;
    },
    addTask(task) {
      this.tasks.push({ ...task, id: Date.now() });
    },
  },
};
</script>