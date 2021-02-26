<template>
  <div class="d-flex flex-column py-5 h-100 sidebarmenu px-4">
    <Avatar />
    <Menu />
    <div style="flex: 1"></div>
    <div class="font-weight-bold"><i class="fas fa-power-off"></i>LOG OUT</div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import MainAvatarVue from "./components/MainAvatar.vue";
import MenuVue from "./components/Menu.vue";
import "./sidebar.scss";

export default Vue.extend({
  components: {
    Avatar: MainAvatarVue,
    Menu: MenuVue,
  },
});
</script>
