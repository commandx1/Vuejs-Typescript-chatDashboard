<template>
  <div
    v-if="
      type === 'file'
        ? msg.content.files
        : type === 'image' && msg.content.images
    "
  >
    <div
      v-for="(file, index) in type === 'file'
        ? msg.content.files
        : type === 'image' && msg.content.images"
      :key="type === 'file' ? index : type === 'image' && index + 1000"
      class="d-flex align-items-center filewrapper px-2"
      :class="{
        'justify-content-end': msg.user === 'You',
        'mt-3': msg.content.text,
      }"
    >
      <div class="filebg d-flex justify-content-center align-items-center">
        <i
          class="far"
          :class="{ 'fa-file': type == 'file', 'fa-image': type == 'image' }"
        ></i>
      </div>
      <div
        class="d-flex"
        :class="{
          'flex-column': msg.user !== 'You',
        }"
      >
        {{ file.name }}
        <span>{{ file.size }} Mb</span>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    msg: Object,
    type: String,
  },
});
</script>