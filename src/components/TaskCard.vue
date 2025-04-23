<template>
  <div :class="['task-card', length, className]">
    <div v-if="length === 'default'">
      <div class="task-title">TASK TITLE</div>
      <p class="short-description">description here</p>
      <IcomoonFreeBin class="icomoon-free-bin" />
      <IconamoonEditLight class="iconamoon-edit-light" />
    </div>
    <div v-if="length === 'longer'" class="overlap">
      <div class="overlap-group">
        <div class="text-wrapper">TASK TITLE</div>
        <p class="div">short description here</p>
      </div>
      <IcomoonFreeBin class="icomoon-free-bin-instance" />
      <IconamoonEditLight class="iconamoon-edit-light-instance" />
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
import IcomoonFreeBin from "./IcomoonFreeBin";
import IconamoonEditLight from "./IconamoonEditLight";

const props = defineProps({
  length: {
    type: String,
    default: "",
  },
  className: {
    type: String,
    default: "",
  },
});
</script>

<style>
.task-card {
  background-color: #787826;
  border-radius: 15px;
  box-shadow: 0px 4px 4px #00000040;
  width: 245px;
}

.task-card .task-title {
  color: #000000;
  font-family: "Inter-Medium", Helvetica;
  font-size: 14px;
  font-weight: 500;
  left: 27px;
  letter-spacing: 0;
  line-height: normal;
  position: absolute;
  top: 19px;
}

.task-card .short-description {
  color: #000000;
  font-family: "Inter-Light", Helvetica;
  font-size: 10px;
  font-weight: 300;
  left: 27px;
  letter-spacing: 0;
  line-height: normal;
  position: absolute;
  top: 41px;
}

.task-card .iconamoon-edit-light {
  height: 15px !important;
  left: 189px !important;
  position: absolute !important;
  top: 12px !important;
  width: 15px !important;
}

.task-card .overlap {
  height: 91px;
  left: 0;
  position: absolute;
  top: 7px;
  width: 191px;
}

.task-card .text-wrapper {
  color: #000000;
  font-family: "Inter-Medium", Helvetica;
  font-size: 14px;
  font-weight: 500;
  left: 1px;
  letter-spacing: 0;
  line-height: normal;
  position: absolute;
  top: 0;
  width: 78px;
}

.task-card .div {
  color: #000000;
  font-family: "Inter-Light", Helvetica;
  font-size: 10px;
  font-weight: 300;
  left: 0;
  letter-spacing: 0;
  line-height: normal;
  position: absolute;
  top: 27px;
  width: 191px;
}

.task-card .iconamoon-edit-light-instance {
  height: 15px !important;
  left: 161px !important;
  position: absolute !important;
  top: 0 !important;
  width: 15px !important;
}

.task-card.longer {
  height: 139px;
}

.task-card.default {
  height: 86px;
  position: relative;
}
</style>
