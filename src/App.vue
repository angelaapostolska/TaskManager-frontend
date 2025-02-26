<script setup>
import TaskForm from "./components/TaskForm.vue";
import TaskList from "./components/TaskList.vue";
import { useTasks } from "./composables/useTasks";

const { tasks, addTask, updateTask } = useTasks();
</script>

<template>
  <div>
    <h1>Your Personal Task Manager</h1>
    <TaskForm @add-task="addTask"></TaskForm>
    <TaskList :tasks="tasks" :update-task="updateTask"></TaskList>
  </div>
</template>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  min-height: 100vh;
  padding: 20px;
  box-sizing: border-box;
}

.task-container {
  width: 80%; /* Increased width to 80% */
  max-width: 900px; /* Increase max-width */
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
  box-sizing: border-box;
}

.task-columns {
  display: flex;
  justify-content: space-between; /* Ensure columns stay side by side */
  gap: 20px;
  width: 100%;
  max-width: 1000px;
  margin-top: 20px;
}

.task-column {
  flex: 1; /* Take equal space */
  min-width: 280px; /* Prevent columns from being too narrow */
  background: #f8f9fa;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(45, 45, 45, 0.1);
}

.task-column:hover {
  transform: translateY(-5px);
  box-shadow: 0px 8px 12px rgba(0, 0, 0, 0.2);
}

h3 {
  text-align: center;
  padding: 10px;
  border-radius: 5px;
  color: white;
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 15px;
}

.urgent {
  background-color: #ff4d4d;
}

.mid {
  background-color: #ffcc00;
}

.least-urgent {
  background-color: #2ecc71;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  align-items: center;
  padding: 10px;
  margin: 5px 0;
  background: white;
  border-radius: 5px;
  border-left: 5px solid #ddd;
  transition: 0.3s;
}

li:hover {
  border-left: 5px solid #007bff;
}

input[type="checkbox"] {
  margin-right: 10px;
  cursor: pointer;
}

.completed {
  text-decoration: line-through;
  color: #999;
}

@media (max-width: 760px) {
  .task-columns {
    flex-direction: column;
    align-items: center;
  }

  .task-column {
    width: 100%; /* Columns take full width on small screens */
    margin-bottom: 20px;
  }

  .task-container {
    width: 100%;
  }
}
</style>
