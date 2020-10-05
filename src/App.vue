<template>
  <main class="mx-auto p-8 container">
    <Menu v-slot="{ open }">
      <MenuButton
        class="px-4 py-2 border border-black rounded flex items-center space-x-2 focus:bg-black hover:bg-black focus:text-white hover:text-white"
      >
        <span>Dropdown</span>
        <svg class="w-4 h-4 transform transition-transform duration-200 ease-in-out" :class="open ? 'rotate-180' : ''" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
      </MenuButton>
      <transition
        enter-active-class="origin-top-left transform transition duration-150 ease-in-out"
        enter-from-class="opacity-0 scale-90 -translate-y-2"
        enter-to-class="opacity-100 scale-100 translate-y-0"
        leave-active-class="origin-top-left transform transition duration-100 ease-in-out"
        leave-from-class="opacity-100 scale-100 translate-y-0"
        leave-to-class="opacity-0 scale-90 -translate-y-2"
      >
        <MenuItems class="mt-2 border border-black rounded max-w-sm flex flex-col divide-y divide-black bg-white shadow-xl focus:outline-none">
          <div class="px-6 py-3 text-xl">
            Signed in as <span class="font-bold">casper@adapt.dk</span>
          </div>
          <MenuItem v-slot="{ active }">
            <a
              href="#dashboard"
              class="px-6 py-2"
              :class="active ? 'bg-black text-white' : ''"
            >
              Dashboard
            </a>
          </MenuItem>
          <MenuItem v-slot="{ active }">
            <a
              href="#settings"
              class="px-6 py-2"
              :class="active ? 'bg-black text-white' : ''"
            >
              Settings
            </a>
          </MenuItem>
          <MenuItem v-slot="{ active }">
            <a
              href="#profile"
              class="px-6 py-2"
              :class="active ? 'bg-black text-white' : ''"
            >
              Profile
            </a>
          </MenuItem>
          <MenuItem v-slot="{ active }">
            <a
              href="#log-out"
              class="px-6 py-2"
              :class="active ? 'bg-black text-white' : ''"
            >
              Log out
            </a>
          </MenuItem>
        </MenuItems>
      </transition>
    </Menu>
  </main>
</template>

<script>
import {
  Menu,
  MenuButton,
  MenuItems,
  MenuItem,
} from '@headlessui/vue';

export default {
  name: 'App',
  components: {
    Menu,
    MenuButton,
    MenuItems,
    MenuItem,
  },
};
</script>
