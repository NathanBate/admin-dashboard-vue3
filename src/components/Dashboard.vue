<template>
  <div class="relative flex globalMenuContainer h-screen" ref="globalMenuContainer">
    <div class="flex w-[275px] bg-[#29333d]  h-screen flex-col slide"
         ref="globalMenu">
      <div class="h-[75px] bg-gray-800 w-full">
        <slot name="identity-header">
          <div class="flex gap-4 items-center w-full h-full px-4">
            <div class="w-[40px] h-[40px]">
              <slot name="brandicon">
                <LetsInnovateIcon class="rounded-full"/>
              </slot>
            </div>
            <div class="text-white font-bold">
              <slot name="brandname">
                <a class="block text-white font-bold" href="https://letsinnovate.io">Let's Innovate, LLC</a>
              </slot>
            </div>

          </div>
        </slot>
      </div>

      <div class="flex flex-col w-full py-4">
        <slot name="menuitems">
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

    <div class="relative flex flex-col w-[100vw] xl:w-[calc(100vw-275px)] h-screen overflow-screen">
      <div class="flex justify-center h-[75px] bg-[#f3f7fc] globalHeaderBar">
        <div class="block xl:hidden">
          <div class="p-5 hover:bg-gray-200 bg-transparent cursor-pointer" @click="toggleGlobalMenu">
            <div class="w-[40px] h-[40px]">
              <MenuIcon class="fill-gray-400"/>
            </div>
          </div>
        </div>
        <div class="flex-auto"></div>
        <div v-show="showSearch" class="w-[75px] h-[75px] p-[10px] hover:bg-gray-200" ref="searchButton">
          <SearchIcon class="fill-gray-400"/>
        </div>
        <div v-show="showUserMenu" class="relative flex items-center w-[75px] h-[75px]">
          <div class="hidden absolute top-[78px] right-0 bg-white shadow-xl shadow-gray-400/20" ref="userMenu">
            <slot name="usermenuitems">
              <a href="#">
                <div class="block py-4 px-4 min-w-[2px] text-black hover:bg-[#f3f7fc]">noreply@letsinnovate.io</div>
              </a>
              <hr>
              <a href="#">
                <div class="block py-4 px-4 min-w-[2px] text-black hover:bg-[#f3f7fc]">Sign Out</div>
              </a>
            </slot>
          </div>
          <div class="w-[75px] h-[75px] p-[10px] hover:bg-gray-200" @click="toggleUserMenu" ref="userMenuButton">
            <slot name="usericon">
              <UserIcon class="rounded-full fill-gray-400"/>
            </slot>
          </div>
        </div>
        <div class="w-5"></div>
      </div>
      <div class="h-full overflow-scroll">
        <slot name="content">
          <div class="p-8">
            Content Here
          </div>
        </slot>
      </div>
    </div>

    <div class="absolute top-0 left-0 w-screen h-screen hidden flex-col justify-center items-center z-80" ref="searchBoxContainer">
      <div class="absolute top-0 left-0 w-screen h-screen bg-black opacity-30 z-95"></div>
      <div class="relative text-black w-full sm:w-2/3 md:w-1/2 z-100 bg-white flex flex-col items-center" ref="searchBox">
        <slot name="searchbar">
          <div class="py-4">Search Bar</div>
        </slot>
        <slot name="searchresults">
          <div class="py-4">Search Results</div>
        </slot>
      </div>
    </div>

  </div>
</template>

<script>
import IconLetsInnovate from './icons/IconLetsInnovate.vue';
import IconCustomers from './icons/IconCustomers.vue';
import IconMenu from './icons/IconMenu.vue';
import IconUserProfile from './icons/IconUserProfile.vue';
import IconSearch from './icons/IconSearch.vue';
import MenuItem from './MenuItem.vue';
import '../assets/main.css';

export default {
  name: "AdminMenuLeftApp",
  components: {
    LetsInnovateIcon : IconLetsInnovate,
    CustomersIcon : IconCustomers,
    MenuIcon : IconMenu,
    UserIcon : IconUserProfile,
    SearchIcon : IconSearch,
    MenuItem : MenuItem
  },
  props: {
    showUserMenu: {
      type: Boolean,
      default: false
    },
    showSearch: {
      type: Boolean,
      default: false
    },
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
        //console.log("Left is now " + computed.getPropertyValue(('left')))
      }
    },
    toggleUserMenu() {
      let userMenu = this.$refs.userMenu
      if (userMenu) {
        let computed = window.getComputedStyle(userMenu)
        let display = computed.getPropertyValue("display")
        if (display === "none") {
          userMenu.style.display = "block"
        } else {
          userMenu.style.display = "none"
        }
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

      let userMenu = this.$refs.userMenu
      let userMenuButton = this.$refs.userMenuButton
      let userMenuComputed = window.getComputedStyle(userMenu)
      let userMenuDisplay = userMenuComputed.getPropertyValue("display")
      if (userMenuDisplay === "block" && !userMenu.contains(event.target) && !userMenuButton.contains(event.target)) {
        userMenu.style.display = "none"
      }

      let searchBox = this.$refs.searchBox
      let searchBoxContainer = this.$refs.searchBoxContainer;
      let searchBoxContainerComputed = window.getComputedStyle(searchBoxContainer)
      let searchBoxContainerDisplay = searchBoxContainerComputed.getPropertyValue('display')

      let searchButton = this.$refs.searchButton;

      let searchBarComputed = window.getComputedStyle(searchBox)
      let searchBarDisplay = searchBarComputed.getPropertyValue("display")

      if (searchBoxContainerDisplay == "flex" && !searchBox.contains(event.target) && !searchButton.contains(event.target)) {
        searchBoxContainer.style.display = "none";
      }
      if (searchBoxContainerDisplay == "none" && searchButton.contains(event.target)) {
        searchBoxContainer.style.display = "flex";
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