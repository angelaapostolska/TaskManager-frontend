<!-- tuka addTask treba da prati api call do BACKEND -->
<script>
import axios from "axios";

export default {
  data() {
    return {
      title: "",
      category: "mid",
    };
  },
  methods: {
    async addTask() {
      await axios.post("http://127.0.0.1:8000/api/tasks", {
        title: this.title,
        category: this.category,
      });
      this.title = "";
      this.category = "mid";
      this.$emit("taskAdded");
    },
  },
};
</script>

<template>
  <form @submit.prevent="addTask">
    <input v-model="title" placeholder="Task title" required />
    <select v-model="category" required>
      <option value="urgent">Urgent</option>
      <option value="mid">Mid</option>
      <option value="least">Least Urgent</option>
    </select>
    <button type="submit">Add Task</button>
  </form>
</template>

<style scoped>
.add-task-form {
  display: flex;
  gap: 8px;
  justify-content: center;
  margin-bottom: 20px;
}
</style>
