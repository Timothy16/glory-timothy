<template>
  <section 
    id="our-story" 
    class="relative py-20 sm:py-32 px-4 sm:px-6 overflow-hidden bg-gradient-to-br from-[#FBF5EA] via-white to-[#FBF5EA]"
  >
    <!-- Decorative Background Elements -->
    <div class="absolute top-20 left-10 w-32 h-32 bg-[#D4A574]/10 rounded-full blur-3xl animate-float"></div>
    <div class="absolute bottom-20 right-10 w-40 h-40 bg-[#C9A96E]/10 rounded-full blur-3xl animate-float-delayed"></div>
    
    <!-- Decorative Corner Elements -->
    <div class="absolute top-0 left-0 w-24 sm:w-32 h-24 sm:h-32 border-t-2 border-l-2 border-[#D4A574]/30"></div>
    <div class="absolute bottom-0 right-0 w-24 sm:w-32 h-24 sm:h-32 border-b-2 border-r-2 border-[#C9A96E]/30"></div>

    <div class="container mx-auto max-w-6xl relative z-10">
      <!-- Section Header -->
      <div 
        ref="headerRef"
        class="text-center mb-16 sm:mb-20 transition-all duration-[1800ms] ease-out"
        :class="{ 'opacity-0 translate-y-10': !headerVisible, 'opacity-100 translate-y-0': headerVisible }"
      >
        <div class="flex items-center justify-center gap-4 mb-4">
          <div class="h-px w-12 sm:w-20 bg-gradient-to-r from-transparent via-[#D4A574] to-[#C9A96E]"></div>
          <svg class="w-6 h-6 sm:w-8 sm:h-8 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
            <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
          </svg>
          <div class="h-px w-12 sm:w-20 bg-gradient-to-l from-transparent via-[#C9A96E] to-[#D4A574]"></div>
        </div>
        
        <h2 class="text-4xl sm:text-5xl md:text-6xl font-bold text-[#3C2A21] mb-3 tracking-wide">
          Our Story
        </h2>
        <p class="text-lg sm:text-xl text-[#D4A574] italic font-light tracking-wider">
          How it all began...
        </p>
      </div>

      <!-- Story Content -->
      <div class="grid md:grid-cols-2 gap-8 sm:gap-12 mb-12">
        <!-- First Story Card -->
        <div 
          ref="card1Ref"
          class="group relative bg-white rounded-2xl p-8 sm:p-10 shadow-lg hover:shadow-2xl transition-all duration-700 border border-[#D4A574]/20"
          :class="{ 'opacity-0 -translate-x-10': !card1Visible, 'opacity-100 translate-x-0': card1Visible }"
        >
          <!-- Decorative Quote Mark -->
          <div class="absolute -top-4 -left-4 text-6xl sm:text-7xl text-[#D4A574]/20 font-serif">"</div>
          
          <div class="relative z-10">
            <div class="flex items-center gap-3 mb-6">
              <div class="w-12 h-12 rounded-full bg-gradient-to-br from-[#D4A574] to-[#C9A96E] flex items-center justify-center">
                <span class="text-white text-xl font-bold">2</span>
              </div>
              <div>
                <p class="text-sm text-[#D4A574] font-medium tracking-wider uppercase">Years Ago</p>
                <p class="text-xs text-[#3C2A21]/60">Where it began</p>
              </div>
            </div>
            
            <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80 mb-4">
              Five years ago, our paths crossed in the most unexpected way, and from that moment, we knew something special was beginning.
            </p>
            
            <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
              Through laughter, adventures, and countless memories, our love has grown stronger with each passing day.
            </p>
          </div>
          
          <!-- Hover Gradient Effect -->
          <div class="absolute inset-0 bg-gradient-to-br from-[#D4A574]/5 to-[#C9A96E]/5 rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700"></div>
        </div>

        <!-- Second Story Card -->
        <div 
          ref="card2Ref"
          class="group relative bg-white rounded-2xl p-8 sm:p-10 shadow-lg hover:shadow-2xl transition-all duration-700 border border-[#C9A96E]/20"
          :class="{ 'opacity-0 translate-x-10': !card2Visible, 'opacity-100 translate-x-0': card2Visible }"
        >
          <!-- Decorative Quote Mark -->
          <div class="absolute -top-4 -right-4 text-6xl sm:text-7xl text-[#C9A96E]/20 font-serif transform rotate-180">"</div>
          
          <div class="relative z-10">
            <div class="flex items-center gap-3 mb-6">
              <div class="w-12 h-12 rounded-full bg-gradient-to-br from-[#C9A96E] to-[#D4A574] flex items-center justify-center">
                <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>
              </div>
              <div>
                <p class="text-sm text-[#C9A96E] font-medium tracking-wider uppercase">Our Journey</p>
                <p class="text-xs text-[#3C2A21]/60">Building forever</p>
              </div>
            </div>
            
            <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80 mb-4">
              We've shared quiet moments and grand adventures, built dreams together, and discovered that home isn't a place—it's being with each other.
            </p>
            
            <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
              Our journey has been filled with love, growth, and the beautiful realization that we want to spend forever together.
            </p>
          </div>
          
          <!-- Hover Gradient Effect -->
          <div class="absolute inset-0 bg-gradient-to-br from-[#C9A96E]/5 to-[#D4A574]/5 rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700"></div>
        </div>
      </div>

      <!-- Timeline Divider -->
      <div 
        ref="timelineRef"
        class="flex items-center justify-center my-12 sm:my-16 transition-all duration-1000"
        :class="{ 'opacity-0 scale-95': !timelineVisible, 'opacity-100 scale-100': timelineVisible }"
      >
        <div class="flex items-center gap-4">
          <div class="w-3 h-3 rounded-full bg-[#D4A574] animate-pulse"></div>
          <div class="h-px w-16 sm:w-32 bg-gradient-to-r from-[#D4A574] to-[#C9A96E]"></div>
          <div class="text-center px-4 sm:px-6 py-3 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] rounded-full">
            <p class="text-white font-medium text-sm sm:text-base tracking-wider">2023 → Forever</p>
          </div>
          <div class="h-px w-16 sm:w-32 bg-gradient-to-l from-[#D4A574] to-[#C9A96E]"></div>
          <div class="w-3 h-3 rounded-full bg-[#C9A96E] animate-pulse"></div>
        </div>
      </div>

      <!-- Bottom Quote -->
      <div 
        ref="quoteRef"
        class="text-center max-w-3xl mx-auto transition-all duration-1000"
        :class="{ 'opacity-0 translate-y-10': !quoteVisible, 'opacity-100 translate-y-0': quoteVisible }"
      >
        <p class="text-2xl sm:text-3xl md:text-4xl font-light text-[#3C2A21] italic leading-relaxed">
          "Our love story is not measured by the calendar's count of days, months, or years.
          <span class="text-[#D4A574] font-medium">It is measured by the profound depth of devotion we intentionally choose and cherish, together, every single day.</span>"
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const headerRef = ref(null)
const card1Ref = ref(null)
const card2Ref = ref(null)
const timelineRef = ref(null)
const quoteRef = ref(null)

const headerVisible = ref(false)
const card1Visible = ref(false)
const card2Visible = ref(false)
const timelineVisible = ref(false)
const quoteVisible = ref(false)

let observer = null

const observeElements = () => {
  const options = {
    threshold: 0.2,
    rootMargin: '0px 0px -100px 0px'
  }

  observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        if (entry.target === headerRef.value) {
          headerVisible.value = true
        } else if (entry.target === card1Ref.value) {
          card1Visible.value = true
        } else if (entry.target === card2Ref.value) {
          card2Visible.value = true
        } else if (entry.target === timelineRef.value) {
          timelineVisible.value = true
        } else if (entry.target === quoteRef.value) {
          quoteVisible.value = true
        }
      }
    })
  }, options)

  if (headerRef.value) observer.observe(headerRef.value)
  if (card1Ref.value) observer.observe(card1Ref.value)
  if (card2Ref.value) observer.observe(card2Ref.value)
  if (timelineRef.value) observer.observe(timelineRef.value)
  if (quoteRef.value) observer.observe(quoteRef.value)
}

onMounted(() => {
  observeElements()
})

onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<style scoped>
@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

@keyframes float-delayed {
  0%, 100% {
    transform: translateY(0px) translateX(0px);
  }
  50% {
    transform: translateY(-15px) translateX(10px);
  }
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animate-float-delayed {
  animation: float-delayed 8s ease-in-out infinite;
}
</style>