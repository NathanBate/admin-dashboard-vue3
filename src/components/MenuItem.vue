<template>
  <a :href="itemLink">
    <div :class="{ 'bg-[#41474D]': linkActive, 'top-level': topLevel, 'second-level': !topLevel}">
      <div v-show="topLevel" class="w-[22px] h-[22px]">
        <slot name="icon">
          <IconDashboard class="fill-white"/>
        </slot>
      </div>
      <div :class="{ 'top-level-label': topLevel, 'second-level-label': !topLevel }">
        <slot name="label">
          Dashboard
        </slot>
      </div>
    </div>
  </a>
</template>

<script>
import IconDashboard from '@/components/icons/IconDashboard.vue';

export default {
  name: "MenuItem",
  components: {
    IconDashboard : IconDashboard
  },
  props: {
    itemLink: {
      type: String,
      default: "/dashboard"
    },
    linkActive: {
      type: Boolean,
      default: false
    },
    topLevel: {
      type: Boolean,
      default: true
    }
  }
}
</script>

<style scoped>
  .top-level {
      @apply flex gap-4 h-[36px] items-center pl-8 pr-4 py-8 hover:bg-gray-800;
  }
  .second-level {
      @apply flex items-center pl-16 pr-4 py-2 hover:bg-gray-800;
  }
  .top-level-label {
      @apply flex-auto text-white font-bold;
  }
  .second-level-label {
      @apply block pl-4 text-sm text-white font-bold;
  }
</style>