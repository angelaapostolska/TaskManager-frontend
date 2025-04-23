<template>
  <div class="search">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="icon"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z"
      />
    </svg>
    <input v-model="searchText" type="text" placeholder="Search.." />
  </div>
</template>

<script setup>
import { ref } from "vue";

const searchText = ref("");
</script>

<style scoped>
.search {
  background-color: #ded2e9b2;
  border: 1px solid #9072ff7a;
  border-radius: 20px;
  box-shadow: 0px 4px 4px #00000040;
  height: 45px;
  width: 348px;
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 0 10px;
}

.icon {
  width: 25px;
  height: 25px;
  color: white;
}

input {
  border: none;
  background: transparent;
  font-size: 14px;
  color: #787878;
  font-family: "Lato", sans-serif;
  width: 100%;
  outline: none;
}
</style>
