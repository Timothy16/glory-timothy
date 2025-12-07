<template>
  <section 
    id="memories" 
    class="relative py-20 sm:py-32 px-4 sm:px-6 overflow-hidden bg-gradient-to-br from-[#3C2A21] via-[#4a3529] to-[#3C2A21]"
  >
    <!-- Decorative Background Pattern -->
    <div class="absolute inset-0 opacity-10">
      <div class="absolute top-20 left-20 w-40 h-40 border border-[#D4A574] rounded-full"></div>
      <div class="absolute bottom-40 right-20 w-32 h-32 border border-[#C9A96E] rounded-full"></div>
      <div class="absolute top-1/2 left-1/3 w-24 h-24 border border-[#D4A574] rounded-full"></div>
    </div>

    <div class="container mx-auto max-w-7xl relative z-10">
      <!-- Section Header -->
      <div 
        ref="headerRef"
        class="text-center mb-16 sm:mb-20 transition-all duration-[1800ms] ease-out"
        :class="{ 'opacity-0 translate-y-10': !headerVisible, 'opacity-100 translate-y-0': headerVisible }"
      >
        <div class="flex items-center justify-center gap-4 mb-4">
          <div class="h-px w-12 sm:w-20 bg-gradient-to-r from-transparent via-[#D4A574] to-[#C9A96E]"></div>
          <svg class="w-6 h-6 sm:w-8 sm:h-8 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
            <path d="M4 3a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V5a2 2 0 00-2-2H4zm12 12H4l4-8 3 6 2-4 3 6z" />
          </svg>
          <div class="h-px w-12 sm:w-20 bg-gradient-to-l from-transparent via-[#C9A96E] to-[#D4A574]"></div>
        </div>
        
        <h2 class="text-4xl sm:text-5xl md:text-6xl font-bold text-white mb-3 tracking-wide">
          Notable Memories
        </h2>
        <p class="text-lg sm:text-xl text-[#D4A574] italic font-light tracking-wider">
          Moments that made our journey beautiful
        </p>
      </div>

      <!-- Photo Gallery Grid -->
      <div 
        ref="galleryRef"
        class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 sm:gap-6 mb-12 sm:mb-16"
      >
        <div
          v-for="(photo, index) in photos"
          :key="photo.id"
          ref="photoRefs"
          :data-index="index"
          class="group relative overflow-hidden rounded-2xl shadow-xl transition-all duration-[1500ms] ease-out cursor-pointer"
          :class="[
            photo.span,
            { 'opacity-0 translate-y-10': !photoVisibility[index], 'opacity-100 translate-y-0': photoVisibility[index] }
          ]"
          :style="{ transitionDelay: `${index * 100}ms` }"
        >
          <!-- Image -->
          <div class="relative w-full h-full overflow-hidden">
            <img
              :src="photo.url"
              :alt="photo.alt"
              class="w-full h-full object-cover transition-all duration-700 ease-out group-hover:scale-110 group-hover:brightness-75"
              :class="photo.height"
            />
          

            <!-- Decorative Corner -->
            <div class="absolute top-2 right-2 w-8 h-8 border-t-2 border-r-2 border-[#C9A96E] opacity-0 group-hover:opacity-100 transition-opacity duration-700"></div>
          </div>
        </div>
      </div>

      <!-- Timeline Footer -->
      <div 
        ref="timelineRef"
        class="transition-all duration-[1800ms] ease-out"
        :class="{ 'opacity-0 scale-95': !timelineVisible, 'opacity-100 scale-100': timelineVisible }"
      >
        <div class="flex flex-col md:flex-row items-center justify-center gap-6 sm:gap-8 bg-white/5 backdrop-blur-sm rounded-3xl p-8 sm:p-10 border border-[#D4A574]/20">
          <!-- Heart Icon -->
          <div class="flex-shrink-0">
            <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-full bg-gradient-to-br from-[#D4A574] to-[#C9A96E] flex items-center justify-center animate-pulse">
              <svg class="w-8 h-8 sm:w-10 sm:h-10 text-white" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
              </svg>
            </div>
          </div>

          <!-- Timeline Text -->
          <div class="text-center md:text-left">
            <h3 class="text-2xl sm:text-3xl md:text-4xl font-bold text-white mb-2 tracking-wide">
              Our Journey
            </h3>
            <div class="flex items-center justify-center md:justify-start gap-3">
              <div class="h-px w-8 sm:w-16 bg-gradient-to-r from-transparent to-[#D4A574]"></div>
              <p class="text-lg sm:text-xl md:text-2xl font-medium text-[#D4A574]">
                March 19, 2023 → Forever
              </p>
              <div class="h-px w-8 sm:w-16 bg-gradient-to-l from-transparent to-[#C9A96E]"></div>
            </div>
          </div>

          <!-- Stats -->
          <div class="flex gap-6 sm:gap-8">
            <div class="text-center">
              <p class="text-3xl sm:text-4xl font-bold text-white mb-1">2+</p>
              <p class="text-xs sm:text-sm text-[#D4A574] tracking-wider uppercase">Years</p>
            </div>
            <div class="w-px h-12 sm:h-14 bg-[#D4A574]/30"></div>
            <div class="text-center">
              <p class="text-3xl sm:text-4xl font-bold text-white mb-1">∞</p>
              <p class="text-xs sm:text-sm text-[#D4A574] tracking-wider uppercase">Memories</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted, reactive } from 'vue'

const headerRef = ref(null)
const galleryRef = ref(null)
const timelineRef = ref(null)
const photoRefs = ref([])

const headerVisible = ref(false)
const timelineVisible = ref(false)
const photoVisibility = reactive({})

let observer = null


const photos = [
  {
    id: 1,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_800,q_auto:good,f_auto/v1765065492/IMG_20250125_094559_ukpxzx.jpg',
    alt: 'Memory 1',
    caption: 'First Dance',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 2,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/v1765065453/IMG_20230407_172420_2_ntmztu.jpg',
    alt: 'Memory 2',
    caption: 'Sunset Together',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 3,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_1200,q_auto:good,f_auto/v1765065456/IMG_20230319_182030_2_ff8ija.jpg',
    alt: 'Memory 3',
    caption: 'Adventure Time',
    span: 'col-span-1 md:col-span-2 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 4,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_800,q_auto:good,f_auto/v1765065464/IMG_20230722_205652_f82lyn.jpg',
    alt: 'Memory 4',
    caption: 'Beach Vibes',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 5,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_800,q_auto:good,f_auto/v1765065490/IMG_20240517_175011_q39aui.jpg',
    alt: 'Memory 5',
    caption: 'City Lights',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 6,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_800,q_auto:good,f_auto/v1765065478/IMG_20240107_083645_vkswec.jpg',
    alt: 'Memory 6',
    caption: 'Special Moment',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 7,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_800,q_auto:good,f_auto/v1765065490/IMG_20241215_214032_fojkoi.jpg',
    alt: 'Memory 7',
    caption: 'Forever Love',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 8,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_1200,q_auto:good,f_auto/v1765065456/IMG-20250601-WA0087_mpxfmh.jpg',
    alt: 'Memory 8',
    caption: 'Golden Hour',
    span: 'col-span-1 md:col-span-2 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 9,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_800,q_auto:good,f_auto/v1765065491/IMG_20241222_180346_zzxvlg.jpg',
    alt: 'Memory 9',
    caption: 'Pure Joy',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  },
  {
    id: 10,
    url: 'https://res.cloudinary.com/dtmt0vas4/image/upload/w_800,q_auto:good,f_auto/v1765065858/INC_0516_ohcfuj.jpg',
    alt: 'Memory 10',
    caption: 'Celebration',
    span: 'col-span-1 row-span-1',
    height: 'h-64 sm:h-80'
  }
]

const observeElements = () => {
  const options = {
    threshold: 0.15,
    rootMargin: '0px 0px -50px 0px'
  }

  observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        if (entry.target === headerRef.value) {
          headerVisible.value = true
        } else if (entry.target === timelineRef.value) {
          timelineVisible.value = true
        } else {
          // For photo elements
          const index = entry.target.dataset.index
          if (index !== undefined) {
            photoVisibility[index] = true
          }
        }
      }
    })
  }, options)

  if (headerRef.value) observer.observe(headerRef.value)
  if (timelineRef.value) observer.observe(timelineRef.value)
  
  // Observe each photo
  photoRefs.value.forEach((photoEl) => {
    if (photoEl) observer.observe(photoEl)
  })
}

onMounted(() => {
  // Initialize all photos as hidden
  photos.forEach((_, index) => {
    photoVisibility[index] = false
  })
  
  observeElements()
})

onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<style scoped>
/* Smooth animations */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>