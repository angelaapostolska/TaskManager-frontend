<script setup>
import TaskForm from "./components/TaskForm.vue";
import TaskList from "./components/TaskList.vue";
import { useTasks } from "./composables/useTasks";

const { tasks, addTask, updateTask } = useTasks();
</script>

<template>
  <div>
    <h1>Your Personal Task Manager</h1>
    <!-- <TaskForm @add-task="addTask"></TaskForm> -->
    <TaskList :tasks="tasks" :update-task="updateTask"></TaskList>
  </div>
</template>
