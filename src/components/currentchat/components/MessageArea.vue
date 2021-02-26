<template>
  <div class="messagearea d-flex align-items-center border-top mx-5">
    <IconButton
      :classes="'position-relative'"
      @clickedToIcon="showMenu = !showMenu"
    >
      <div
        :class="{ show: showMenu }"
        class="position-absolute d-flex flex-column"
      >
        <IconButton v-for="icon in menuGroup" :key="icon" v-html="icon" />
      </div>
      <i class="pointer fas fa-plus"></i>
    </IconButton>
    <input type="text" placeholder="Type a message here" class="mx-3" />
    <i class="far fa-smile"></i>
    <IconButton>
      <i class="fas fa-location-arrow"></i>
    </IconButton>
  </div>
</template>

<script lang="ts">
import IconButtonVue from "@/components/IconButton.vue";
import Vue from "vue";
export default Vue.extend({
  components: {
    IconButton: IconButtonVue,
  },
  data() {
    return {
      showMenu: false,
      menuGroup: [
        '<i class="fas fa-microphone"></i>',
        '<i class="far fa-image"></i>',
        '<i class="far fa-file"></i>',
      ],
    };
  },
});
</script>