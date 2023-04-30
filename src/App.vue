<template>
  <div class="flex globalMenuContainer" ref="globalMenuContainer">

      <div class="flex w-[275px] bg-[#29333d]  h-screen flex-col slide"
           ref="globalMenu">
        <div class="h-[75px] bg-gray-800 w-full">
          <slot name="identity-header">
            <div class="flex gap-4 items-center w-full h-full px-4">
              <div class="w-[40px] h-[40px]">
                <slot name="brandIcon">
                  <LetsInnovateIcon class="rounded-full"/>
                </slot>
              </div>
              <slot name="brandName">
                <a class="block text-white font-bold" href="https://letsinnovate.io">Let's Innovate, LLC</a>
              </slot>
            </div>
          </slot>
        </div>

        <div class="flex flex-col w-full py-4">
          <slot name="menuItems">
            <MenuItem :link-active="true" />
            <MenuItem item-link="/customers">
              <template v-slot:icon>
                <CustomersIcon class="fill-white"/>
              </template>
              <template v-slot:label>
                Customers
              </template>
            </MenuItem>
            <MenuItem item-link="#" :top-level="false">
              <template v-slot:label>
                Sublink 1
              </template>
            </MenuItem>
            <MenuItem item-link="/customer/report" :top-level="false" :link-active="true">
              <template v-slot:label>
                Sublink 2
              </template>
            </MenuItem>
            <MenuItem item-link="/customer/report" :top-level="false">
              <template v-slot:label>
                Sublink 3
              </template>
            </MenuItem>
          </slot>
        </div>
      </div>

    <div class="flex flex-col w-[100vw] xl:w-[calc(100vw-275px)]">
      <div class="flex justify-center h-[75px] bg-[#f3f7fc] globalHeaderBar">
        <div class="block xl:hidden">
          <div class="p-5 hover:bg-gray-200 bg-transparent cursor-pointer" @click="toggleGlobalMenu">
            <div class="w-[40px] h-[40px]">
              <MenuIcon class="fill-gray-400"/>
            </div>
          </div>
        </div>
        <div class="flex-auto"></div>
        <div class="flex items-center p-5 hover:bg-gray-200">
          <div class="w-[65px] h-[65px]">
            <UserIcon class="rounded-full fill-gray-400"/>
          </div>
        </div>
      </div>
      <div>
        <slot name="content">
          <div class="p-8">
            Content Here
          </div>
        </slot>
      </div>
    </div>
  </div>
</template>

<script>
import IconLetsInnovate from '@/components/icons/IconLetsInnovate.vue';
import IconCustomers from '@/components/icons/IconCustomers.vue';
import IconMenu from '@/components/icons/IconMenu.vue';
import IconUserProfile from '@/components/icons/IconUserProfile.vue';
import MenuItem from '@/components/MenuItem.vue';

export default {
  name: "AdminMenuLeftApp",
  components: {
    LetsInnovateIcon : IconLetsInnovate,
    CustomersIcon : IconCustomers,
    MenuIcon : IconMenu,
    UserIcon : IconUserProfile,
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
        console.log("Left is now " + computed.getPropertyValue(('left')))
      }
    },
  }, // methods
  mounted() {

    window.addEventListener('resize', ()=> {
      let globalMenuContainer = this.$refs.globalMenuContainer
      if (globalMenuContainer) {
        if (window.innerWidth >= 1280) {
          globalMenuContainer.style.left = "0"
        } else {
          globalMenuContainer.style.left = "-275px"
        }
      }
    })

    document.addEventListener('click', (event)=> {
      let globalMenuContainer = this.$refs.globalMenuContainer
      let globalMenu = this.$refs.globalMenu
      let globalMenuComputed = window.getComputedStyle(globalMenuContainer)
      let globalMenuLeft = globalMenuComputed.getPropertyValue('left')
      let ww = window.innerWidth;
      if (globalMenuLeft == '0px' && !globalMenu.contains(event.target) && ww < 1280) {
        globalMenuContainer.style.left = "-275px";
      }
    })

  }
}
</script>

<style>
.globalMenuContainer {
    @apply relative -left-[275px] w-[calc(100vw+275px)] xl:left-0 xl:w-[100vw];
    transition: left 0.25s ease-out;
}
.globalHeaderBar {
    @apply mb-6 shadow-xl shadow-gray-400/20;
}

</style>