<template>
  <a :href="itemLink">
    <div class="flex gap-4 h-[36px] items-center pl-8 pr-4 py-8 hover:bg-gray-800"
    :class="{ 'bg-[#41474D]': linkActive}">
      <div class="w-[22px] h-[22px]">
        <slot name="icon">
          <IconDashboard class="fill-white"/>
        </slot>
      </div>
      <div class="flex-auto text-white font-bold">
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
    }
  }
}
</script>