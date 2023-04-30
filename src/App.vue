<template>
  <div class="flex">
    <transition name="slide">
      <div v-if="globalMenu" class="flex w-[275px] bg-[#29333d]  h-screen flex-col"
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
    </transition>

    <div class="block xl:hidden">
      <div class="p-4 hover:bg-gray-200 cursor-pointer" @click="toggleGlobalMenu">
        <div class="w-[50px] h-[50px]">
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
      globalMenu: true,
    }
  },
  methods: {
    toggleGlobalMenu() {
        if (this.globalMenu === false) {
          this.globalMenu = true
        } else {
          this.globalMenu = false;
        }
    }
  },
  created() {
    if (window.innerWidth <= 1280) {
      this.globalMenu = false;
    }
  }
}
</script>

<style>
.slide-enter-active,
.slide-leave-active
{
    transition: transform 0.5s ease;
}

.slide-enter,
.slide-leave-to {
    transform: translateX(-100%);
    transition: all 0.5s ease;
}


</style>