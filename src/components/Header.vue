<template>
  <div class="header-row">
    <div class="hello-user">Hello {{ userName }}!</div>
    <div class="right">
      <div class="plus-icon-wrapper" @click="handleClick">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="plus-icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M12 4.5v15m7.5-7.5h-15"
          />
        </svg>
      </div>
      <SearchBar />
    </div>
  </div>
</template>

<script setup>
import SearchBar from "./SearchBar.vue";
import { ref } from "vue";

const emit = defineEmits(["show-form"]);
const userName = ref("Jane Doe");

const handleClick = () => {
  emit("show-form");
};
</script>

<style scoped>
.header-row {
  position: fixed;
  top: 0;
  left: 100px; /* Sidebar width */
  right: 0;
  height: 80px;
  z-index: 10;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  padding-left: 30px;
  padding-right: 30px;
  background-color: white;
}

.right {
  display: flex;
  gap: 10px;
  align-items: center;
  margin-right: 30px;
}

.hello-user {
  /* apply correct font styling */
  color: #49484a;
  font-family: "Playfair Display";
  font-size: 40px;
  font-style: normal;
  font-weight: 600;
  line-height: 28px;
}

.plus-icon-wrapper {
  width: 50px;
  height: 50px;
  background-color: #e8dff0;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  cursor: pointer;
  transition: transform 0.2s ease-in-out;
}

.plus-icon-wrapper:hover {
  transform: scale(1.05);
}

.plus-icon-wrapper svg {
  width: 24px;
  height: 24px;
  color: white;
}
@media (max-width: 768px) {
  .header-row {
    left: 0;
    right: 0;
    flex-direction: column;
    justify-content: center;
    height: auto;
    padding: 15px 20px;
  }

  .hello-user {
    font-size: 30px;
    margin-bottom: 10px;
  }

  .right {
    margin-right: 0;
    flex-direction: row;
    width: 100%;
    justify-content: space-between;
  }

  .plus-icon-wrapper {
    margin-left: 10px;
  }
}
</style>
