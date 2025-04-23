<!-- home page, prikazhuenje na tasks -->
<template>
  <!-- header-->
  <Header></Header>
  <!-- main content -->
  <div class="main-content-container">
    <p>our tasks will come here</p>
  </div>
  <!-- sidebar -->
  <Sidebar></Sidebar>
</template>
<script setup>
import SearchBar from "./SearchBar.vue";
import Sidebar from "./Sidebar.vue";
import Header from "./Header.vue";
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
.main-content-container {
  margin-left: 100px; /* space for the sidebar */
  margin-top: 100px; /* space for the header */
  padding: 20px;
  height: calc(100vh - 100px);
  overflow-y: auto;
}
.profile-icon-wrapper,
.question-icon-wrapper,
.settings-icon-wrapper {
  width: 70px;
  height: 70px;
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
.profile-icon-wrapper:hover,
.question-icon-wrapper:hover,
.settings-icon-wrapper:hover {
  transform: scale(1.05);
}
.profile-icon-wrapper svg,
.question-icon-wrapper svg,
.settings-icon-wrapper svg {
  width: 30px;
  height: 30px;
}
</style>
