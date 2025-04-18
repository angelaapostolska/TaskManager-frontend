<!-- kolonoite za prikaz na task -->
<template>
  <div class="home-screen">
    <div class="overlap-group-wrapper">
      <div class="overlap-group">
        <div class="overlap">
          <!-- INLINE SEARCH BAR + ICON -->
          <div class="search-instance design-component-instance-node">
            <!-- text input -->
            <input
              type="text"
              placeholder="Search..."
              class="search-2"
              @input="onSearch"
            />
            <!-- Heroicon goes next to it -->
            <SearchIcon class="search-icon" />
          </div>
          <div class="text-wrapper">Hello, user</div>

          <div class="group">
            <PlusIcon class="plus-icon" />
          </div>

          <CogIcon class="settings-icon" />
        </div>

        <div class="iconamoon-profile-wrapper">
          <UserIcon class="user-icon" />
        </div>

        <div class="solid-question-wrapper">
          <QuestionMarkCircleIcon class="questionMark-icon" />
        </div>

        <div class="solar-settings-wrapper">
          <CogIcon class="settings-icon" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {
  SearchIcon,
  PlusIcon,
  UserIcon,
  CogIcon,
  QuestionMarkCircleIcon,
} from "@heroicons/vue/24/outline";

export default {
  name: "HomeScreen",
  components: {
    SearchIcon,
    PlusIcon,
    UserIcon,
    CogIcon,
    QuestionMarkCircleIcon,
    CogIcon,
  },
};
</script>

<style>
.home-screen {
  background-color: #ffffff;
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 100%;
}

.home-screen .overlap-group-wrapper {
  background-color: #ffffff;
  height: 982px;
  width: 1512px;
}

.home-screen .overlap-group {
  background-image: url(./image-2.png);
  background-position: 50% 50%;
  background-size: cover;
  height: 982px;
  position: relative;
}

.home-screen .overlap {
  background-color: #ffffff;
  height: 982px;
  left: 103px;
  position: absolute;
  top: 0;
  width: 1409px;
}

.home-screen .search-instance {
  border: unset !important;
  border-color: unset !important;
  left: 1015px !important;
  position: absolute !important;
  top: 69px !important;
  width: 348px !important;
}

.home-screen .design-component-instance-node {
  left: 86px !important;
  top: 13px !important;
}

.home-screen .search-2 {
  left: 33px !important;
  top: 10px !important;
  width: 41px !important;
}

.home-screen .text-wrapper {
  color: #49484a;
  font-family: "Playfair Display-SemiBold", Helvetica;
  font-size: 40px;
  font-weight: 600;
  left: 42px;
  letter-spacing: 0;
  line-height: 28px;
  position: absolute;
  top: 78px;
  white-space: nowrap;
}

.home-screen .group {
  background-color: #e8dff0;
  border-radius: 25px;
  box-shadow: 0px 4px 4px #00000040;
  height: 50px;
  left: 937px;
  position: absolute;
  top: 67px;
  width: 50px;
}

.home-screen .ic-round-plus {
  height: 30px !important;
  left: 10px !important;
  position: absolute !important;
  top: 10px !important;
  width: 30px !important;
}

.home-screen .material-symbols {
  height: 24px !important;
  left: 641px !important;
  position: absolute !important;
  top: 479px !important;
  width: 24px !important;
}

.home-screen .iconamoon-profile-wrapper {
  background-color: #cdb7ff80;
  border-radius: 35px;
  box-shadow: 0px 4px 4px #00000040;
  height: 70px;
  left: 16px;
  position: absolute;
  top: 48px;
  width: 70px;
}

.home-screen .iconamoon-profile {
  height: 35px !important;
  left: 17px !important;
  position: absolute !important;
  top: 17px !important;
  width: 35px !important;
}

.home-screen .solid-question-wrapper {
  background-color: #cdb7ff80;
  border-radius: 35px;
  box-shadow: 0px 4px 4px #00000040;
  height: 70px;
  left: 16px;
  position: absolute;
  top: 771px;
  width: 70px;
}

.home-screen .fa-solid-question {
  left: 27px !important;
  top: 23px !important;
}

.home-screen .solar-settings-wrapper {
  background-color: #cdb7ff80;
  border-radius: 35px;
  box-shadow: 0px 4px 4px #00000040;
  height: 70px;
  left: 16px;
  position: absolute;
  top: 861px;
  width: 70px;
}

.home-screen .solar-settings {
  height: 30px !important;
  left: 20px !important;
  position: absolute !important;
  top: 20px !important;
  width: 30px !important;
}
.search-instance {
  position: absolute !important;
  left: 1015px !important;
  top: 69px !important;
  width: 348px !important;
  display: flex;
  align-items: center;
  background: #fff;
  border-radius: 8px;
  padding: 4px 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.search-2 {
  flex: 1;
  border: none;
  outline: none;
  font-size: 16px;
  color: #49484a;
}

.search-icon {
  width: 24px;
  height: 24px;
  color: #888;
  cursor: pointer;
  margin-left: 8px;
}
</style>
