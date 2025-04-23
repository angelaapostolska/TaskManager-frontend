<!-- korisnikot da dodava sopstvena kategorija?? isto prakja API calls to backend -->
<script>
import axios from "axios";

export default {
  data() {
    return {
      name: "",
    };
  },
  methods: {
    async addCategory() {
      try {
        await axios.post("http://127.0.0.1:8000/api/categories", {
          name: this.name,
        });
        this.$emit("categoryAdded");
        this.name = "";
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>

<template>
  <form @submit.prevent="addCategory" class="add-category-form">
    <input v-model="name" placeholder="Category name" required />
    <button type="submit">Add Category</button>
  </form>
</template>

<style scoped>
.add-category-form {
  display: flex;
  gap: 8px;
  justify-content: center;
  margin-bottom: 20px;
}
</style>
