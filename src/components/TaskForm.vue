<!-- formata za dodavanje novi tasks na FRONTEND -->
<!-- form for adding a new task -->
<script setup>
import { computed, ref } from "vue";

//emit function to pass the task to the parent component
const emit = defineEmits(["add-task"]);

const taskName = ref("");
const urgencies = ["Urgent", "Mid", "Least Urgent"];
const selectedUrgency = ref(null);

//computed property for dynamic class based on what state is selected
const urgencyClass = computed(() => {
  switch (selectedUrgency.value) {
    case "Urgent":
      return "urgent";
    case "Mid":
      return "mid";
    case "Least Urgent":
      return "least-urgent";
    default:
      return "";
  }
});

//function that handles task submission
const addTask = () => {
  if (!taskName.value || selectedUrgency.value === null) {
    alert("Please enter a task name and select an urgency!");
    return;
  }

  //emit the data for the current task to the parent component
  emit("add-task", {
    name: taskName.value,
    urgency: selectedUrgency.value,
    completed: false,
  });

  //clearing inputs after emiting the event
  taskName.value = "";
  selectedUrgency.value = null;
};
</script>
<template>
  <div class="task-container">
    <label for="taskName">Task Name: </label>
    <input
      id="taskName"
      v-model="taskName"
      type="text"
      placeholder="Enter task name"
    />

    <label for="urgency">Select Urgency: </label>
    <select v-model="selectedUrgency" class="dropdown">
      <option value="" disabled>Select urgency</option>
      <option
        v-for="(urgency, index) in urgencies"
        :key="index"
        :value="urgency"
      >
        {{ urgency }}
      </option>
    </select>

    <button @click="addTask" class="submit-button">Add Task</button>
  </div>
</template>

<style scoped>
.task-container {
  width: 80%; /* Increased form width */
  max-width: 900px; /* Maximum width for form */
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
  background: #f9f9f9;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

input,
select {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
  width: 100%; /* Make sure inputs take full width */
}

.submit-button {
  padding: 10px 20px;
  background-color: #6d8aa8;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.submit-button:hover {
  background-color: #47668b;
}

label {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 5px;
}

.dropdown {
  cursor: pointer;
}
</style>
