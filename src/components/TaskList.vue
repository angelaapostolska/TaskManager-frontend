<script>
import axios from "axios";

export default {
  data() {
    return {
      tasks: []
    };
  },
  computed: {
    // Group tasks by category name
    groupedTasks() {
      const groups = {};
      this.tasks.forEach((task) => {
        const categoryName = task.category ? task.category.name : "Uncategorized";
        if (!groups[categoryName]) groups[categoryName] = [];
        groups[categoryName].push(task);
      });
      return groups;
    }
  },
  methods: {
    async fetchTasks() {
      try {
        const response = await axios.get("http://127.0.0.1:8000/api/tasks");
        this.tasks = response.data;
      } catch (error) {
        console.error(error);
      }
    },
    async toggleTask(task) {
      try {
        await axios.put(`http://127.0.0.1:8000/api/tasks/${task.id}`, {
          completed: !task.completed
        });
        this.fetchTasks();
      } catch (error) {
        console.error(error);
      }
    }
  },
  mounted() {
    this.fetchTasks();
  }
};
</script>

<template>
  <div class="task-list-container">
    <h2 class="task-list-title">Task List</h2>

    <div v-for="(tasks, categoryName) in groupedTasks" :key="categoryName">
      <h3 class="category-title">{{ categoryName }}</h3>
      <ul>
        <li
            v-for="task in tasks"
            :key="task.id"
            :class="{ completed: task.completed }"
        >
          <span>
            {{ task.title }}
          </span>
          <button @click="toggleTask(task)">
            {{ task.completed ? "Undo" : "Done" }}
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.task-list-container {
  background-color: #fff;
  border-radius: 8px;
  margin: 0 auto;
  padding: 20px;
  max-width: 600px;
  text-align: left;
}

.task-list-title {
  text-align: center;
  margin-bottom: 20px;
  color: #333;
  font-size: 1.5rem;
}

.category-title {
  margin-top: 20px;
  margin-bottom: 10px;
  color: #666;
  font-size: 1.2rem;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  background-color: #f9f9f9;
  border-radius: 5px;
  margin-bottom: 8px;
  padding: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.completed {
  text-decoration: line-through;
  color: #999;
}

button {
  background-color: #007BFF;
  border: none;
  color: #fff;
  padding: 6px 12px;
  border-radius: 4px;
  cursor: pointer;
  margin-left: 10px;
}

button:hover {
  background-color: #0056b3;
}
</style>