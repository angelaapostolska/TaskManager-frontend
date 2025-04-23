<script setup>
import { useTasks } from "./composables/useTasks";
import HomeScreen from "./components/HomeScreen.vue";

const { tasks, addTask, updateTask } = useTasks();
</script>

<template>
  <div>
    <!-- <TaskForm @add-task="addTask"></TaskForm> -->
    <HomeScreen :tasks="tasks" :update-task="updateTask"></HomeScreen>
  </div>
</template>
