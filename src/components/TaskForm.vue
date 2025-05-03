<!-- formata za dodavanje novi tasks na FRONTEND -->
<!-- form for adding a new task -->
<script setup>
import { computed, ref } from "vue";

//emit function to pass the task to the parent component
const emit = defineEmits(["add-task"]);

const taskName = ref("");
const taskDescription = ref("");
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
    description: taskDescription.value,
    completed: false,
  });

  //clearing inputs after emiting the event
  taskName.value = "";
  selectedUrgency.value = null;
  taskDescription.value = "";
};
</script>
<template>
  <div class="form-wrapper">
    <div class="image-container">
      <div class="illustration-container"></div>
    </div>

    <div class="task-form">
      <label for="taskName">Task Name:</label>
      <input
        id="taskName"
        v-model="taskName"
        type="text"
        placeholder="Enter task name"
      />

      <label for="urgency">Category:</label>
      <select v-model="selectedUrgency">
        <option disabled value="">Select urgency</option>
        <option
          v-for="(urgency, index) in urgencies"
          :key="index"
          :value="urgency"
        >
          {{ urgency }}
        </option>
      </select>

      <label for="description">Description:</label>
      <textarea
        id="description"
        v-model="taskDescription"
        placeholder="Enter task description"
      ></textarea>

      <button class="custom-btn" @click="addTask">Submit</button>
    </div>
  </div>
</template>

<style scoped>
.form-wrapper {
  width: 682px;
  height: 441px;
  display: flex; /* side-by-side layout */
  flex-direction: row;
  background: #f9f9f9;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

/* left side */
.image-container {
  width: 50%;
  height: 100%;
  background-image: url("/taskFormBg.png"); /* This is correct if it's in public/ */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
}
.illustration-container {
  background-image: url("/graphic.png");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 200px;
  height: 200px;
}

/* right side - the form */
.task-form {
  width: 50%;
  height: 100%;
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  box-sizing: border-box;
  justify-content: center;
}

/* Button styling */
.custom-btn {
  display: flex;
  width: 300px;
  height: 45px;
  justify-content: center;
  align-items: center;
  flex-shrink: 0;
  border-radius: 15px;
  background: var(--Disabled, rgba(177, 148, 255, 0.15));
  color: white;
  font-family: "Lato", sans-serif;
  font-weight: 600;
  font-size: 18px;
  border: none;
  cursor: pointer;
  transition: background 0.3s ease;
  margin-top: 80px;
}

.custom-btn:hover {
  background: rgba(177, 148, 255, 0.25);
}

input,
select,
textarea {
  width: 100%; /* Make them take up all available width */
  max-width: 300px; /* Prevent them from stretching too wide */
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
  box-sizing: border-box; /* Include padding in the width calculation */
}

label {
  font-weight: bold;
  font-size: 14px;
  margin-bottom: 4px;
}
</style>
