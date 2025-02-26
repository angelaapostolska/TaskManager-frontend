<script setup>
import { defineProps } from "vue";

// Expect tasks array and updateTask function to be passed in as props
defineProps(["tasks", "updateTask"]);
</script>

<template>
  <div class="task-columns">
    <!-- Urgent Column -->
    <div class="task-column urgent">
      <h3>Urgent</h3>
      <ul>
        <li
          v-for="task in tasks.filter((task) => task.urgency === 'Urgent')"
          :key="task.id"
          :class="{ completed: task.completed }"
        >
          <input
            type="checkbox"
            :v-model="task.completed"
            @change="updateTask(task)"
          />
          <span>{{ task.name }}</span>
        </li>
      </ul>
    </div>

    <!-- Mid Column -->
    <div class="task-column mid">
      <h3>Mid</h3>
      <ul>
        <li
          v-for="task in tasks.filter((task) => task.urgency === 'Mid')"
          :key="task.id"
          :class="{ completed: task.completed }"
        >
          <input
            type="checkbox"
            :v-model="task.completed"
            @change="updateTask(task)"
          />
          <span>{{ task.name }}</span>
        </li>
      </ul>
    </div>

    <!-- Least Urgent Column -->
    <div class="task-column least-urgent">
      <h3>Least Urgent</h3>
      <ul>
        <li
          v-for="task in tasks.filter(
            (task) => task.urgency === 'Least Urgent'
          )"
          :key="task.id"
          :class="{ completed: task.completed }"
        >
          <input
            type="checkbox"
            :v-model="task.completed"
            @change="updateTask(task)"
          />
          <span>{{ task.name }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
/* Container for all task columns */
.task-columns {
  display: flex;
  justify-content: space-between;
  gap: 20px;
  width: 100%;
  margin-top: 20px;
}

/* Each individual column */
.task-column {
  flex: 1;
  min-width: 250px;
  background: #f8f9fa;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.task-column:hover {
  transform: translateY(-5px);
  box-shadow: 0px 8px 12px rgba(0, 0, 0, 0.2);
}

/* Headers for each column */
.task-column h3 {
  text-align: center;
  padding: 10px;
  border-radius: 5px;
  color: white;
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 15px;
}

/* Urgency-specific header colors */
.urgent h3 {
  background-color: #882a2a;
}

.mid h3 {
  background-color: #e8cf61;
}

.least-urgent h3 {
  background-color: #31955b;
}

/* Task list styling */
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

/* Checkbox styling */
input[type="checkbox"] {
  margin-right: 10px;
  cursor: pointer;
}

/* Style for completed tasks */
.completed {
  text-decoration: line-through;
  color: #999;
}
span {
  white-space: normal;
  overflow-wrap: break-word;
  word-break: break-word;
}

/* Responsive adjustments */
@media (max-width: 760px) {
  .task-columns {
    flex-direction: column;
    align-items: center;
  }
  .task-column {
    width: 100%;
    margin-bottom: 20px;
  }
}
</style>
