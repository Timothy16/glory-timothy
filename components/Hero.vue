<template>
  <section class="relative h-screen w-full overflow-hidden mt-[72px] sm:mt-[84px]">
    <!-- Image Carousel -->
    <div class="absolute inset-0">
      <transition-group
        name="fade-slide"
        tag="div"
        class="relative w-full h-full"
      >
        <div
          v-for="(image, index) in images"
          :key="image.id"
          v-show="currentSlide === index"
          class="absolute inset-0 w-full h-full"
        >
          <!-- Mobile Images -->
          <img
            :src="mobileImages[index].url"
            :alt="mobileImages[index].alt"
            :loading="index === 0 ? 'eager' : 'lazy'"
            class="md:hidden w-full h-full object-cover object-top"
          />
          <!-- Desktop Images -->
          <img
            :src="desktopImages[index].url"
            :alt="desktopImages[index].alt"
            :loading="index === 0 ? 'eager' : 'lazy'"
            class="hidden md:block w-full h-full object-cover object-top"
          />
          <!-- Gradient Overlay -->
          <div class="absolute inset-0 bg-gradient-to-b from-[#3C2A21]/40 via-[#3C2A21]/50 to-[#3C2A21]/70"></div>
        </div>
      </transition-group>
    </div>

    <!-- Content -->
    <div class="relative z-20 h-full flex flex-col items-center justify-center px-4 sm:px-6">
      <div class="text-center space-y-6 sm:space-y-8 max-w-4xl mx-auto">
        <!-- Decorative Line -->
        <div class="flex items-center justify-center gap-4 animate-fade-in">
          <div class="h-px w-12 sm:w-20 bg-gradient-to-r from-transparent to-[#C9A96E]"></div>
          <div class="w-2 h-2 rounded-full bg-[#C9A96E] animate-pulse"></div>
          <div class="h-px w-12 sm:w-20 bg-gradient-to-l from-transparent to-[#C9A96E]"></div>
        </div>

        <!-- Main Heading -->
        <div class="space-y-3 sm:space-y-4 animate-slide-up" style="animation-delay: 0.2s">
          <h1 class="text-5xl sm:text-6xl md:text-7xl lg:text-8xl font-bold text-white leading-tight tracking-wide">
            We Are Getting
          
          <span class="text-5xl sm:text-6xl md:text-7xl lg:text-8xl font-bold bg-gradient-to-r from-[#D4A574] to-[#C9A96E] bg-clip-text text-transparent leading-tight tracking-wide">
            Married!
          </span></h1>
        </div>

        <!-- Subtitle -->
        <p class="text-lg sm:text-xl md:text-2xl text-white/90 font-light tracking-wide animate-fade-in" style="animation-delay: 0.4s">
          Join us as we celebrate our love and step into forever.
        </p>

        <!-- Decorative Divider -->
        <div class="flex items-center justify-center gap-2 py-4 animate-fade-in" style="animation-delay: 0.5s">
          <div class="w-1 h-1 rounded-full bg-[#C9A96E]/60"></div>
          <div class="w-1.5 h-1.5 rounded-full bg-[#C9A96E]/80"></div>
          <div class="w-2 h-2 rounded-full bg-[#C9A96E]"></div>
          <div class="w-1.5 h-1.5 rounded-full bg-[#C9A96E]/80"></div>
          <div class="w-1 h-1 rounded-full bg-[#C9A96E]/60"></div>
        </div>

        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row gap-4 sm:gap-6 items-center justify-center animate-slide-up" style="animation-delay: 0.6s">
          <a
            href="https://drive.google.com/drive/folders/1zHp7wmcOp0oF_mb7E0FRIbkLLOskozhU"
            target="_blank"
            class="group relative px-6 sm:px-8 py-3 sm:py-4 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] text-white text-sm sm:text-base md:text-lg font-medium tracking-wider rounded-full overflow-hidden transition-all duration-300 hover:shadow-2xl hover:shadow-[#C9A96E]/50 hover:scale-105 active:scale-95 w-auto"
          >
            <span class="relative z-10">Download Pictures</span>
            <div class="absolute inset-0 bg-gradient-to-r from-[#C9A96E] to-[#D4A574] opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          </a>
        </div>
      </div>

      <!-- Carousel Indicators -->
      <div class="absolute bottom-8 sm:bottom-12 left-0 right-0 flex justify-center items-center gap-3">
        <button
          v-for="(image, index) in images"
          :key="`indicator-${image.id}`"
          @click="goToSlide(index)"
          :aria-label="`Go to slide ${index + 1}`"
          class="group relative"
        >
          <div
            class="w-2.5 h-2.5 rounded-full transition-all duration-300"
            :class="[
              currentSlide === index
                ? 'bg-[#C9A96E] scale-125'
                : 'bg-white/40 hover:bg-white/60 hover:scale-110'
            ]"
          ></div>
          <!-- Active indicator glow -->
          <div
            v-if="currentSlide === index"
            class="absolute inset-0 w-2.5 h-2.5 rounded-full bg-[#C9A96E] animate-ping opacity-75"
          ></div>
        </button>
      </div>

      <!-- Scroll Indicator -->
      <div class="absolute bottom-24 sm:bottom-28 left-1/2 -translate-x-1/2 animate-bounce hidden sm:block">
        <div class="flex flex-col items-center gap-2">
          <span class="text-white/60 text-sm tracking-wider">Scroll</span>
          <svg class="w-6 h-6 text-[#C9A96E]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
          </svg>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlide = ref(0)
let intervalId = null

// Desktop images - Optimized with Cloudinary transformations
const desktopImages = [
  {
    id: 1,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_1920,q_auto:good,f_auto/v1765058600/GT_001_web_hkpuvk.jpg',
    alt: 'Wedding celebration moment 1'
  },
  {
    id: 2,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_1920,q_auto:good,f_auto/v1765054925/GT_013__web_fumxqo.jpg',
    alt: 'Wedding celebration moment 2'
  },
  {
    id: 3,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_1920,q_auto:good,f_auto/v1765058605/GT_004_Web_kxzokf.jpg',
    alt: 'Wedding celebration moment 3'
  },
  {
    id: 4,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_1920,q_auto:good,f_auto/v1765058600/GT_007_web_py6szk.jpg',
    alt: 'Wedding celebration moment 4'
  },
  {
    id: 5,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_1920,q_auto:good,f_auto/v1765061020/GT_014_web_2_iyznar.jpg',
    alt: 'Wedding celebration moment 5'
  }
]

// Mobile images - Optimized with Cloudinary transformations
const mobileImages = [
  {
    id: 1,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_768,q_auto:good,f_auto/v1765052197/GT_001_dw7j27.jpg',
    alt: 'Wedding celebration moment 1'
  },
  {
    id: 2,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_768,q_auto:good,f_auto/v1765059596/GT_013_Graded_jr0mzt.jpg',
    alt: 'Wedding celebration moment 2'
  },
  {
    id: 3,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_768,q_auto:good,f_auto/v1765061229/GT_004_Graded_fq65dw.jpg',
    alt: 'Wedding celebration moment 3'
  },
  {
    id: 4,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_768,q_auto:good,f_auto/v1765059670/GT_007_Graded_izvnx5.jpg',
    alt: 'Wedding celebration moment 4'
  },
  {
    id: 5,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_768,q_auto:good,f_auto/v1765061019/GT_014_Graded_2_ucgbv2.jpg',
    alt: 'Wedding celebration moment 5'
  }
]

// Use desktop images for carousel indicators
const images = desktopImages

const goToSlide = (index) => {
  currentSlide.value = index
  resetInterval()
}

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % images.length
}

const resetInterval = () => {
  if (intervalId) {
    clearInterval(intervalId)
  }
  startAutoplay()
}

const startAutoplay = () => {
  intervalId = setInterval(() => {
    nextSlide()
  }, 8000)
}

onMounted(() => {
  startAutoplay()
})

onUnmounted(() => {
  if (intervalId) {
    clearInterval(intervalId)
  }
})
</script>

<style scoped>
/* Fade and slide transition for carousel */
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: all 2s ease;
}

.fade-slide-enter-from {
  opacity: 0;
  transform: scale(1.05);
}

.fade-slide-leave-to {
  opacity: 0;
  transform: scale(0.98);
}

/* Custom animations */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fadeIn 1s ease-out backwards;
}

.animate-slide-up {
  animation: slideUp 1s ease-out backwards;
}

/* Smooth scroll */
html {
  scroll-behavior: smooth;
}
</style>