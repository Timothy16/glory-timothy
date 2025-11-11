<template>
  <nav class="fixed top-0 left-0 right-0 z-50 bg-[#FBF5EA] backdrop-blur-sm shadow-lg transition-all duration-300">
    <div class="container mx-auto px-4 sm:px-6 py-4 flex flex-row w-full items-center justify-between">
      <!-- Logo -->
      <button 
        @click="scrollToTop"
        class="flex items-center transform transition-all duration-300 hover:scale-105"
      >
        <div class="relative">
          <div class="text-2xl sm:text-3xl font-bold text-[#3C2A21] tracking-wider">
            G <span class="text-[#D4A574]">&</span> T
          </div>
          <div class="absolute -bottom-1 left-0 right-0 h-0.5 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] transform scale-x-0 transition-transform duration-300 group-hover:scale-x-100"></div>
        </div>
      </button>

      <!-- Desktop Navigation -->
      <div class="hidden md:flex items-center gap-8 lg:gap-12">
        <a
          v-for="link in navLinks"
          :key="link.href"
          :href="link.href"
          class="nav-link relative text-[15px] font-medium tracking-wider text-[#3C2A21] transition-all duration-300 hover:text-[#D4A574] group"
        >
          {{ link.text }}
          <span class="absolute -bottom-1 left-0 right-0 h-0.5 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] transform scale-x-0 transition-transform duration-300 group-hover:scale-x-100 origin-left"></span>
        </a>
      </div>

      <!-- CTA Button Desktop -->
      <div 
        class="hidden md:block px-6 cursor-pointer py-3 bg-[#3C2A21] text-[#C9A96E] text-[15px] font-medium tracking-wider rounded-lg transition-all duration-300 hover:bg-[#D4A574] hover:text-white hover:shadow-lg hover:scale-105 active:scale-95"
        @click="getDirections"
      >
        Get Directions
      </div>

      <!-- Mobile Menu Button -->
      <button 
        @click="toggleMenu"
        class="md:hidden p-2 text-[#3C2A21] hover:text-[#D4A574] transition-colors duration-300 relative z-50"
        aria-label="Toggle menu"
      >
        <svg 
          class="w-6 h-6 transform transition-transform duration-300"
          :class="{ 'rotate-90': isMenuOpen }"
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
    <transition
      enter-active-class="transition-all duration-300 ease-out"
      enter-from-class="opacity-0 -translate-y-4"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-4"
    >
      <div 
        v-if="isMenuOpen"
        class="md:hidden absolute top-full left-0 right-0 bg-[#FBF5EA] shadow-xl border-t border-[#D4A574]/20"
      >
        <div class="container mx-auto px-6 py-6 space-y-4">
          <a
            v-for="(link, index) in navLinks"
            :key="link.href"
            :href="link.href"
            @click="closeMenu"
            class="block py-3 px-4 text-[15px] font-medium tracking-wider text-[#3C2A21] hover:text-[#D4A574] hover:bg-[#D4A574]/10 rounded-lg transition-all duration-300 transform hover:translate-x-2"
            :style="{ animationDelay: `${index * 50}ms` }"
          >
            {{ link.text }}
          </a>
          
          <div 
            class="pt-4 border-t border-[#D4A574]/20"
          >
            <button
              @click="getDirections"
              class="w-full py-3 px-4 bg-[#3C2A21] text-[#C9A96E] text-[15px] font-medium tracking-wider rounded-lg transition-all duration-300 hover:bg-[#D4A574] hover:text-white hover:shadow-lg active:scale-95"
            >
              Get Directions
            </button>
          </div>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const navLinks = [
  { text: 'Our Story', href: '#our-story' },
  { text: 'Proposal', href: '#proposal' },
  { text: 'Memories', href: '#memories' },
  { text: 'Gift Us', href: '#gift-us' }
]

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

const getDirections = () => {
  // Add your Google Maps link or location here
  window.open('https://maps.google.com', '_blank')
  closeMenu()
}
</script>

<style scoped>
/* Smooth scroll behavior */
html {
  scroll-behavior: smooth;
}

/* Custom animations for nav items */
@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateX(-20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.nav-link {
  animation: slideIn 0.3s ease-out backwards;
}

.nav-link:nth-child(1) { animation-delay: 0.1s; }
.nav-link:nth-child(2) { animation-delay: 0.2s; }
.nav-link:nth-child(3) { animation-delay: 0.3s; }
.nav-link:nth-child(4) { animation-delay: 0.4s; }
</style>