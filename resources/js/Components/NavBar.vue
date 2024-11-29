<template>
  <nav 
    class="fixed w-full top-0 z-50 transition-all duration-300"
    :class="[
      scrolled ? 'bg-white shadow-md' : 'bg-transparent',
      scrolled ? 'text-text' : 'text-white'
    ]"
  >
    <div class="container mx-auto px-4">
      <div class="flex justify-between items-center py-4">
        <!-- Logo -->
        <Link :href="route('home')" class="flex items-center">
          <img 
            src="/images/logo.png" 
            alt="MicroFinance Logo" 
            class="w-16 h-12 md:w-20 md:h-15" 
          />
          <span 
            class="ml-2 text-lg md:text-xl font-bold"
            :class="scrolled ? 'text-secondary' : 'text-white'"
          >
            M.A.M Financial
          </span>
        </Link>
        
        <!-- Desktop Menu -->
        <ul class="hidden md:flex space-x-6">
          <li v-for="(link, index) in links" :key="index">
            <Link 
              :href="route(link.route)" 
              class="transition-colors"
              :class="[
                scrolled ? 'text-text hover:text-secondary' : 'text-white hover:text-gray-200'
              ]"
            >
              {{ link.name }}
            </Link>
          </li>
        </ul>

        <!-- Mobile Menu Button -->
        <button 
          class="md:hidden p-2"
          @click="isMenuOpen = !isMenuOpen"
          :aria-expanded="isMenuOpen"
          aria-label="Toggle menu"
        >
          <svg 
            class="w-6 h-6"
            :class="scrolled ? 'text-text' : 'text-white'"
            fill="none" 
            stroke="currentColor" 
            viewBox="0 0 24 24"
          >
            <path 
              v-if="!isMenuOpen"
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M4 6h16M4 12h16M4 18h16"
            />
            <path 
              v-else
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div 
        v-show="isMenuOpen"
        class="md:hidden"
      >
        <div 
          class="px-2 pt-2 pb-3 space-y-1 bg-white shadow-lg rounded-lg mt-2"
          :class="{ 'animate-fade-in-down': isMenuOpen }"
        >
          <Link 
            v-for="(link, index) in links" 
            :key="index"
            :href="route(link.route)" 
            class="block px-3 py-2 rounded-md text-base font-medium text-text hover:text-secondary hover:bg-gray-50 transition-colors"
            @click="isMenuOpen = false"
          >
            {{ link.name }}
          </Link>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Link } from '@inertiajs/vue3'

const scrolled = ref(false)
const isMenuOpen = ref(false)

const links = [
  { name: 'Home', route: 'home' },
  { name: 'About', route: 'about' },
  { name: 'Contact Us', route: 'contact' }
]

const handleScroll = () => {
  scrolled.value = window.scrollY > 50
}

// Close mobile menu when resizing to desktop
const handleResize = () => {
  if (window.innerWidth >= 768) { // md breakpoint
    isMenuOpen.value = false
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  window.addEventListener('resize', handleResize)
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', handleResize)
})
</script>

<style scoped>
nav {
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
}

/* Animation for mobile menu */
.animate-fade-in-down {
  animation: fadeInDown 0.3s ease-out;
}

@keyframes fadeInDown {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Optional: Add transition for mobile menu height */
[v-show] {
  transition: all 0.3s ease-in-out;
}
</style>