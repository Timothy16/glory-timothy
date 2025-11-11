<template>
  <section 
    id="proposal" 
    class="relative py-20 sm:py-32 px-4 sm:px-6 bg-white overflow-hidden"
  >
    <!-- Decorative Background -->
    <div class="absolute top-0 right-0 w-64 h-64 bg-[#D4A574]/5 rounded-full blur-3xl"></div>
    <div class="absolute bottom-0 left-0 w-80 h-80 bg-[#C9A96E]/5 rounded-full blur-3xl"></div>

    <div class="container mx-auto max-w-7xl relative z-10">
      <!-- Section Header -->
      <div 
        ref="headerRef"
        class="text-center mb-16 sm:mb-20 transition-all duration-[1800ms] ease-out"
        :class="{ 'opacity-0 translate-y-10': !headerVisible, 'opacity-100 translate-y-0': headerVisible }"
      >
        <div class="inline-block mb-4">
          <div class="flex items-center gap-3 px-6 py-2 bg-gradient-to-r from-[#D4A574]/10 to-[#C9A96E]/10 rounded-full border border-[#D4A574]/20">
            <svg class="w-5 h-5 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
              <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
            </svg>
            <span class="text-sm font-medium text-[#3C2A21] tracking-wider uppercase">The Big Moment</span>
          </div>
        </div>
        
        <h2 class="text-4xl sm:text-5xl md:text-6xl font-bold text-[#3C2A21] mb-3 tracking-wide">
          The Proposal
        </h2>
        <p class="text-lg sm:text-xl text-[#D4A574] italic font-light tracking-wider">
          The moment we said "Forever"
        </p>
      </div>

      <!-- Content Grid -->
      <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
        <!-- Image Carousel -->
        <div 
          ref="carouselRef"
          class="order-2 lg:order-1 transition-all duration-[1600ms] ease-out"
          :class="{ 'opacity-0 -translate-x-10': !carouselVisible, 'opacity-100 translate-x-0': carouselVisible }"
        >
          <div class="relative group">
            <!-- Main Carousel Container -->
            <div class="relative w-full h-[400px] sm:h-[500px] lg:h-[600px] overflow-hidden rounded-3xl shadow-2xl">
              <transition-group
                name="carousel-fade"
                tag="div"
                class="relative w-full h-full"
              >
                <div
                  v-for="(image, index) in proposalImages"
                  :key="image.id"
                  v-show="currentSlide === index"
                  class="absolute inset-0 w-full h-full"
                >
                  <img
                    :src="image.url"
                    :alt="image.alt"
                    class="w-full h-full object-cover"
                  />
                  <!-- Subtle Overlay -->
                  <div class="absolute inset-0 bg-gradient-to-t from-[#3C2A21]/30 via-transparent to-transparent"></div>
                </div>
              </transition-group>

              <!-- Navigation Arrows -->
              <button
                @click="prevSlide"
                class="absolute left-4 top-1/2 -translate-y-1/2 bg-white/90 hover:bg-white text-[#3C2A21] p-3 rounded-full transition-all duration-500 ease-out opacity-0 group-hover:opacity-100 hover:scale-110 active:scale-95 shadow-lg z-20"
                aria-label="Previous image"
              >
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                </svg>
              </button>
              
              <button
                @click="nextSlide"
                class="absolute right-4 top-1/2 -translate-y-1/2 bg-white/90 hover:bg-white text-[#3C2A21] p-3 rounded-full transition-all duration-500 ease-out opacity-0 group-hover:opacity-100 hover:scale-110 active:scale-95 shadow-lg z-20"
                aria-label="Next image"
              >
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                </svg>
              </button>

              <!-- Image Counter -->
              <div class="absolute top-4 right-4 bg-[#3C2A21]/80 backdrop-blur-sm text-white px-4 py-2 rounded-full text-sm font-medium">
                {{ currentSlide + 1 }} / {{ proposalImages.length }}
              </div>
            </div>

            <!-- Carousel Indicators -->
            <div class="flex justify-center gap-3 mt-6">
              <button
                v-for="(image, index) in proposalImages"
                :key="`indicator-${image.id}`"
                @click="goToSlide(index)"
                :aria-label="`Go to slide ${index + 1}`"
                class="transition-all duration-500 ease-out rounded-full"
                :class="[
                  currentSlide === index
                    ? 'w-12 h-3 bg-gradient-to-r from-[#D4A574] to-[#C9A96E]'
                    : 'w-3 h-3 bg-[#3C2A21]/20 hover:bg-[#3C2A21]/40'
                ]"
              ></button>
            </div>
          </div>
        </div>

        <!-- Story Content -->
        <div 
          ref="storyRef"
          class="order-1 lg:order-2 space-y-6 sm:space-y-8 transition-all duration-[1600ms] ease-out"
          :class="{ 'opacity-0 translate-x-10': !storyVisible, 'opacity-100 translate-x-0': storyVisible }"
        >
          <!-- Decorative Element -->
          <div class="flex items-center gap-4">
            <div class="w-16 h-px bg-gradient-to-r from-[#D4A574] to-transparent"></div>
            <svg class="w-8 h-8 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
            </svg>
          </div>

          <!-- Story Text -->
          <div class="space-y-6">
            <p class="text-base sm:text-lg lg:text-xl leading-relaxed text-[#3C2A21]/80">
              Under a sky painted with stars, with hearts full of love and dreams of tomorrow, the question was asked and answered with joyful tears and an enthusiastic "Yes!"
            </p>
            
            <div class="relative pl-6 border-l-2 border-[#D4A574]/30">
              <p class="text-base sm:text-lg lg:text-xl leading-relaxed text-[#3C2A21]/80">
                It was a moment we'll cherish forever—the beginning of our next chapter, surrounded by love and the promise of a beautiful future together.
              </p>
            </div>

            <div class="bg-gradient-to-br from-[#D4A574]/10 to-[#C9A96E]/10 rounded-2xl p-6 sm:p-8 border border-[#D4A574]/20">
              <p class="text-lg sm:text-xl font-medium text-[#3C2A21] italic leading-relaxed">
                "In that perfect moment, time stood still, and our hearts spoke the language of forever."
              </p>
            </div>
          </div>

          <!-- CTA Button -->
          <div class="pt-4">
            <a
              href="https://unsplash.com/collections/proposal"
              target="_blank"
              class="group inline-flex items-center gap-3 px-8 py-4 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] text-white text-base sm:text-lg font-medium tracking-wider rounded-full transition-all duration-500 ease-out hover:shadow-2xl hover:shadow-[#C9A96E]/50 hover:scale-105 active:scale-95"
            >
              <span>View All Photos</span>
              <svg class="w-5 h-5 transform group-hover:translate-x-1 transition-transform duration-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const headerRef = ref(null)
const carouselRef = ref(null)
const storyRef = ref(null)

const headerVisible = ref(false)
const carouselVisible = ref(false)
const storyVisible = ref(false)

const currentSlide = ref(0)
let intervalId = null

// Using Unsplash proposal/engagement images
const proposalImages = [
  {
    id: 1,
    url: 'https://images.unsplash.com/photo-1522673607200-164d1b6ce486?w=1920&q=80',
    alt: 'Proposal moment 1'
  },
  {
    id: 2,
    url: 'https://images.unsplash.com/photo-1470428938184-3b96c79d856b?w=1920&q=80',
    alt: 'Proposal moment 2'
  },
  {
    id: 3,
    url: 'https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?w=1920&q=80',
    alt: 'Proposal moment 3'
  },
  {
    id: 4,
    url: 'https://images.unsplash.com/photo-1465495976277-4387d4b0b4c6?w=1920&q=80',
    alt: 'Proposal moment 4'
  }
]

const goToSlide = (index) => {
  currentSlide.value = index
  resetInterval()
}

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % proposalImages.length
  resetInterval()
}

const prevSlide = () => {
  currentSlide.value = currentSlide.value === 0 
    ? proposalImages.length - 1 
    : currentSlide.value - 1
  resetInterval()
}

const resetInterval = () => {
  if (intervalId) {
    clearInterval(intervalId)
  }
  startAutoplay()
}

const startAutoplay = () => {
  intervalId = setInterval(() => {
    currentSlide.value = (currentSlide.value + 1) % proposalImages.length
  }, 6000) // 6 seconds for smooth, relaxed transitions
}

const observeElements = () => {
  const options = {
    threshold: 0.2,
    rootMargin: '0px 0px -100px 0px'
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        if (entry.target === headerRef.value) {
          headerVisible.value = true
        } else if (entry.target === carouselRef.value) {
          carouselVisible.value = true
        } else if (entry.target === storyRef.value) {
          storyVisible.value = true
        }
      }
    })
  }, options)

  if (headerRef.value) observer.observe(headerRef.value)
  if (carouselRef.value) observer.observe(carouselRef.value)
  if (storyRef.value) observer.observe(storyRef.value)
}

onMounted(() => {
  observeElements()
  startAutoplay()
})

onUnmounted(() => {
  if (intervalId) {
    clearInterval(intervalId)
  }
})
</script>

<style scoped>
/* Smooth carousel fade transition */
.carousel-fade-enter-active,
.carousel-fade-leave-active {
  transition: all 1.2s ease-in-out;
}

.carousel-fade-enter-from {
  opacity: 0;
  transform: scale(1.05);
}

.carousel-fade-leave-to {
  opacity: 0;
  transform: scale(0.98);
}
</style>