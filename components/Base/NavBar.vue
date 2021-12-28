<template>
  <nav class="bg-white shadow-lg">
    <div class="max-w-6xl mx-auto px-4">
      <div class="flex justify-between">
        <!-- logo -->
        <div>
          <a href="#" class="flex items-center py-4 px-2">
            <span class="font-semibold text-gray-500 text-lg">
              Navigation
            </span>
          </a>
        </div>
        <!-- primary navbar items -->
        <div class="hidden md:flex items-center space-x-1">
          <a
            v-for="option in options"
            :key="option.title"
            :href="option.link"
            @click="activateOption(option)"
            :class="{'border-b-3 border-green-500': option.isActive }"
            class="py-4 px-2 text-green-500 font-semibold"
          >
            {{ option.title }}
          </a>
        </div>

        <!-- secundary navbar items -->
        <div class="hidden md:flex items-center space-x-3">
          <a href="#" class="py-4 px-2 font-medium text-gray-500 rounded hover:text-green-500 transition duration-300">Login</a>
          <a href="" class="py-2 px-2 font-medium text-white bg-green-500 rounded hover:bg-green-400 transition duration-300">
            Sign Up
          </a>
        </div>

        <!-- mobile menu button -->
        <div class="md:hidden flex items-center">
          <button @click="showMenu=!showMenu" class="outline-none mobile-menu-button">
            <svg
              class="w-6 h-6 text-gray-500"
              x-show="!showMenu"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
            <path d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
  
    <!-- Mobile menu -->
    <div v-show="showMenu" class="mobile-menu">
      <ul class="">
        <li
           v-for="option in options"
          :key="option.title"
          :class="{ 'active': option.isActive }"
        >
          <a
            :href="option.link"
            :class="{'bg-green-500 font-semibold': option.isActive }"
            class="block text-sm px-2 py-4 hover:bg-green-500 transition duration-300"
          >
            {{ option.title }}
          </a>
        </li>        
      </ul>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'
const showMenu = ref(false)
interface menuOption {
  title: string,
  link: string,
  isActive: Boolean,
}

const options = reactive([
  {
    title: 'Home',
    link: '#',
    isActive: true,
  },
  {
    title: 'Services',
    link: '#',
    isActive: false,
  },
  {
    title: 'About',
    link: '#',
    isActive: false,
  },
  {
    title: 'Contact Us',
    link: '#',
    isActive: false,
  },
])

function activateOption (option: menuOption) {
  options.forEach(optionMenu=> optionMenu.isActive = false )
  const selected = options.find(o=> o.title === option.title )
  if (!!selected) selected.isActive = true
}


</script>

<style scoped>
</style>