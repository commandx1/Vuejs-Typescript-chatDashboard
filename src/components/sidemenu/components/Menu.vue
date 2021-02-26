<template>
  <ul class="list-unstyled mt-4">
    <li :key="item.id" v-for="item in menu" :class="{ active: item.isActive }">
      <a :href="item.href" v-html="item.content"></a>
    </li>
  </ul>
</template>

:<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  data() {
    return {
      menu: [
        {
          id: 1,
          href: "#",
          content: '<i class="fas fa-home"></i>HOME',
          isActive: false,
        },
        {
          id: 2,
          href: "#",
          content: '<i class="fas fa-comment-dots"></i>CHAT',
          isActive: true,
        },
        {
          id: 3,
          href: "#",
          content: '<i class="far fa-user"></i>CONTACT',
          isActive: false,
        },
        {
          id: 4,
          href: "#",
          content: '<i class="far fa-bell"></i>NOTIFICATIONS',
          isActive: false,
        },
        {
          id: 5,
          href: "#",
          content: '<i class="far fa-calendar-minus"></i>CALENDAR',
          isActive: false,
        },
        {
          id: 6,
          href: "#",
          content: '<i class="fas fa-cog"></i>SETTINGS',
          isActive: false,
        },
      ],
    };
  },
});
</script>