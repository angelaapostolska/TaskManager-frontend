<script>
import AddCategory from "./components/AddCategory.vue";
import AddTask from "./components/AddTask.vue";
import TaskList from "./components/TaskList.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    AddCategory,
    AddTask,
    TaskList,
  },
  data() {
    return {
      categories: [],
    };
  },
  methods: {
    async refreshCategories() {
      try {
        const res = await axios.get("http://127.0.0.1:8000/api/categories");
        this.categories = res.data;
      } catch (error) {
        console.error(error);
      }
    },
    refreshTasks() {
      this.$refs.taskList.fetchTasks();
    },
  },
  mounted() {
    this.refreshCategories();
  },
};
</script>

<template>
  <div class="app-container">
    <h1 class="app-title">Task Manager</h1>

    <AddCategory @categoryAdded="refreshCategories" />

    <AddTask
        :categories="categories"
        @taskAdded="refreshTasks"
    />

    <TaskList ref="taskList" />
  </div>
</template>

<style scoped>
.app-container {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f5f5f5;
  min-height: 100vh;
  margin: 0;
  padding: 40px 0;
}

.app-title {
  color: #4CAF50;
  font-size: 2.5rem;
  margin-bottom: 30px;
}
</style>
