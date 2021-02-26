<template>
  <div id="app" class="h-100">
    <ChatDashboard />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import ChatDashboardVue from "./components/ChatDashboard.vue";

export default Vue.extend({
  name: "App",
  components: {
    ChatDashboard: ChatDashboardVue,
  },
});
</script>

<style lang="scss">
@import "./variables.scss";
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  height: 100vh;
  color: $lightgrey;
  background: linear-gradient(to right, #f3f3fb, #fdfbfd);
  font-size: $fontsize-md;
}
</style>
