<template>
  <div>
    <div v-if="content.files && type === 'file'" class="files py-2 px-3">
      <i class="far fa-file-alt"></i>
      {{ fileCounter(content.files) }}
    </div>
    <div v-if="content.images && type === 'image'" class="photo py-2 px-3">
      <i class="far fa-image"></i>
      Photo {{ fileCounter(content.images) }}
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: { content: Object, type: String },
  methods: {
    fileCounter(file: []) {
      if (this.type === "file") {
        return file.length > 1 ? "Files (x" + file.length + ")" : "File";
      }
      if (this.type === "photo") {
        return file.length > 1 ? "(x" + file.length + ")" : "";
      }
    },
  },
});
</script>