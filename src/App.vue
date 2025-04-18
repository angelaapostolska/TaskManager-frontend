<script setup>
import { useTasks } from "./composables/useTasks";
import HomeScreen from "./components/HomeScreen.vue";

const { tasks, addTask, updateTask } = useTasks();
</script>

<template>
  <div>
    <h1>Your Personal Task Manager</h1>
    <!-- <TaskForm @add-task="addTask"></TaskForm> -->
    <HomeScreen :tasks="tasks" :update-task="updateTask"></HomeScreen>
  </div>
</template>
