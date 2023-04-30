<template>
  <div class="flex globalMenuContainer" ref="globalMenuContainer">

      <div class="flex w-[275px] bg-[#29333d]  h-screen flex-col slide"
           ref="globalMenu">
        <div class="h-[75px] bg-gray-800 w-full">
          <slot name="identity-header">
            <div class="flex gap-4 items-center w-full h-full px-4">
              <div class="w-[40px] h-[40px]">
                <LetsInnovateIcon class="rounded-full"/>
              </div>
              <a class="block text-white font-bold" href="https://letsinnovate.io">Let's Innovate, LLC</a>
            </div>
          </slot>
        </div>

        <div class="flex flex-col w-full py-4">
          <MenuItem :link-active="true" />
          <MenuItem item-link="/customers">
            <template v-slot:icon>
              <CustomersIcon class="fill-white"/>
            </template>
            <template v-slot:label>
              Customers
            </template>
          </MenuItem>
        </div>
      </div>

    <div class="block xl:hidden">
      <div class="p-4 hover:bg-gray-200 bg-transparent cursor-pointer" @click="toggleGlobalMenu">
        <div class="w-[40px] h-[40px]">
          <MenuIcon class="fill-gray-400"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import IconLetsInnovate from '@/components/icons/IconLetsInnovate.vue';
import IconCustomers from '@/components/icons/IconCustomers.vue';
import IconMenu from '@/components/icons/IconMenu.vue';
import MenuItem from '@/components/MenuItem.vue';

export default {
  name: "AdminMenuLeftApp",
  components: {
    LetsInnovateIcon : IconLetsInnovate,
    CustomersIcon : IconCustomers,
    MenuIcon : IconMenu,
    MenuItem : MenuItem
  },
  data() {
    return {
    }
  },
  methods: {
    toggleGlobalMenu() {
      let globalMenuContainer = this.$refs.globalMenuContainer
      if (globalMenuContainer) {
        let computed = window.getComputedStyle(globalMenuContainer)
        let left = computed.getPropertyValue("left")
        if (left === "0px") {
          globalMenuContainer.style.left = "-275px"
        } else {
          globalMenuContainer.style.left = "0"
        }
      }
    }
  },
}
</script>

<style>
.globalMenuContainer {
    @apply relative -left-[275px] xl:left-[0] w-[calc(100vw+275px)] xl:w-[100vw];
    transition: left 0.25s ease-out;
}

</style>