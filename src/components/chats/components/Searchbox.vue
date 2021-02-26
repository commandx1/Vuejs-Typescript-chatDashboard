<template>
  <Paper :classes="'mt-4'">
    <div class="row mx-0">
      <div class="col-9 p-3 searchbox">
        <i class="fas fa-search"></i>
        <input type="text" placeholder="Search" />
      </div>
      <div class="col-3 p-3 d-flex align-items-center justify-content-center">
        <span>Messages</span>
        <i class="fas fa-chevron-down"></i>
      </div>
    </div>
  </Paper>
</template>
<script lang="ts">
import PaperVue from "@/components/Paper.vue";
import Vue from "vue";
export default Vue.extend({
  components: {
    Paper: PaperVue,
  },
});
</script>