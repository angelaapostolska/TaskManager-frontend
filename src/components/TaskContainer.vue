<template>
  <div class="task-container">
    <h2 class="div-title">Your Tasks</h2>
    <div class="columns">
      <div class="column">
        <div class="header-row">
          <h3>Urgent</h3>
          <div class="plus-icon-wrapper">
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
        </div>
      </div>
      <div class="column">
        <div class="header-row">
          <h3>Mid</h3>
          <div class="plus-icon-wrapper">
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
        </div>
      </div>
      <div class="column">
        <div class="header-row">
          <h3>Low</h3>
          <div class="plus-icon-wrapper">
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
        </div>
      </div>
    </div>
  </div>
</template>
<script setup></script>
<style>
.task-container {
  width: 920px;
  height: 600px;
  background-color: #eeeeef;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  padding: 0.5rem 2rem 2rem 2rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  overflow-y: auto;
  margin-left: 10px;
}
.div-title {
  font-family: "Playfair Display";
  font-weight: 600;
  color: #49484a;
  font-size: 40px;
  line-height: 28px;
}
.columns {
  display: flex;
  gap: 1rem;
  flex: 1;
}
.column {
  flex: 1;
  border-radius: 12px;
  padding: 1rem;
}
.plus-icon-wrapper {
  width: 30px;
  height: 30px;
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
.header-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 0.5rem; /* spacing from tasks below */
}
.header-row h3 {
  color: #49484a;
  font-family: Inter;
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  text-transform: uppercase;
}
</style>
