<template>
  <footer class="relative overflow-hidden">
    <!-- Main Footer -->
    <div 
      class="relative py-16 sm:py-20 px-4 sm:px-6 bg-gradient-to-br from-[#3C2A21] via-[#4a3529] to-[#3C2A21]"
    >
      <!-- Decorative Background Pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute top-10 left-10 w-40 h-40 border border-[#D4A574] rounded-full"></div>
        <div class="absolute bottom-20 right-20 w-32 h-32 border border-[#C9A96E] rounded-full"></div>
        <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-64 h-64 border border-[#D4A574] rounded-full"></div>
      </div>

      <!-- Floating Elements -->
      <div class="absolute top-20 right-1/4 w-2 h-2 bg-[#C9A96E] rounded-full animate-float opacity-60"></div>
      <div class="absolute bottom-32 left-1/3 w-3 h-3 bg-[#D4A574] rounded-full animate-float-delayed opacity-60"></div>

      <div class="container mx-auto max-w-4xl relative z-10">
        <!-- Logo/Couple Names -->
        <div 
          ref="logoRef"
          class="flex justify-center mb-8 sm:mb-12 transition-all duration-[1800ms] ease-out"
          :class="{ 'opacity-0 scale-90': !logoVisible, 'opacity-100 scale-100': logoVisible }"
        >
          <div class="text-center">
            <div class="inline-flex items-center gap-4 mb-4">
              <div class="h-px w-12 sm:w-20 bg-gradient-to-r from-transparent to-[#D4A574]"></div>
              <svg class="w-10 h-10 sm:w-12 sm:h-12 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
              </svg>
              <div class="h-px w-12 sm:w-20 bg-gradient-to-l from-transparent to-[#C9A96E]"></div>
            </div>
            <h3 class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-2 tracking-wider">
              Glory <span class="text-[#D4A574]">&</span> <span class="text-[#C9A96E]">Timothy</span>
            </h3>
            <p class="text-[#D4A574] text-sm sm:text-base tracking-widest uppercase">Forever Begins Here</p>
          </div>
        </div>

        <!-- Quote Section -->
        <div 
          ref="quoteRef"
          class="transition-all duration-[1800ms] ease-out mb-12"
          :class="{ 'opacity-0 translate-y-10': !quoteVisible, 'opacity-100 translate-y-0': quoteVisible }"
        >
          <div class="relative">
            <!-- Quote Marks -->
            <div class="absolute -top-6 left-0 text-6xl sm:text-7xl text-[#D4A574]/20 font-serif leading-none">"</div>
            
            <p class="text-base sm:text-lg md:text-xl text-white/90 text-center leading-relaxed italic px-8 sm:px-16 py-8" style="font-family: Georgia, serif;">
              A successful marriage requires falling in love many times, always with the same person. Two souls with but a single thought, two hearts that beat as one. Thank you for celebrating this special moment with us and for the love and joy you bring to our lives.
            </p>
            
            <div class="absolute -bottom-6 right-0 text-6xl sm:text-7xl text-[#C9A96E]/20 font-serif leading-none transform rotate-180">"</div>
          </div>
        </div>

       

        <!-- Divider -->
        <div class="flex items-center justify-center gap-4 mb-8">
          <div class="h-px w-20 sm:w-32 bg-gradient-to-r from-transparent via-[#D4A574] to-[#C9A96E]"></div>
          <div class="w-2 h-2 rounded-full bg-[#C9A96E]"></div>
          <div class="h-px w-20 sm:w-32 bg-gradient-to-l from-transparent via-[#C9A96E] to-[#D4A574]"></div>
        </div>

        <!-- Navigation Links -->
        <div 
          ref="navRef"
          class="flex flex-wrap justify-center gap-6 sm:gap-8 mb-8 transition-all duration-[1800ms] ease-out"
          :class="{ 'opacity-0 translate-y-10': !navVisible, 'opacity-100 translate-y-0': navVisible }"
        >
          <a
            v-for="link in footerLinks"
            :key="link.href"
            :href="link.href"
            class="text-white/70 hover:text-[#C9A96E] text-sm sm:text-base font-medium tracking-wider transition-all duration-300 hover:scale-110"
          >
            {{ link.text }}
          </a>
        </div>
      </div>
    </div>

    <!-- Copyright Bar - ALWAYS VISIBLE -->
    <div class="bg-[#2a1f18] py-6 px-4 sm:px-6">
      <div class="container mx-auto max-w-6xl">
        <div class="flex flex-col sm:flex-row items-center justify-center gap-3 sm:gap-4 flex-wrap text-center">
          <div class="flex items-center gap-2">
            <!-- <svg class="w-5 h-5 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM8.736 6.979C9.208 6.193 9.696 6 10 6c.304 0 .792.193 1.264.979a1 1 0 001.715-1.029C12.279 4.784 11.232 4 10 4s-2.279.784-2.979 1.95c-.285.475-.507 1-.67 1.55H6a1 1 0 000 2h.013a9.358 9.358 0 000 1H6a1 1 0 100 2h.351c.163.55.385 1.075.67 1.55C7.721 15.216 8.768 16 10 16s2.279-.784 2.979-1.95a1 1 0 10-1.715-1.029c-.472.786-.96.979-1.264.979-.304 0-.792-.193-1.264-.979a4.265 4.265 0 01-.264-.521H10a1 1 0 100-2H8.017a7.36 7.36 0 010-1H10a1 1 0 100-2H8.472c.08-.185.167-.36.264-.521z" clip-rule="evenodd" />
            </svg> -->
           <span class="text-[#C9A96E]">&copy;</span> 
            <span class="font-semibold text-white/70 text-sm sm:text-base">2025</span>
          </div>
          
          <span class="hidden sm:block w-1 h-1 rounded-full bg-white/30"></span>
          
          <span class="text-white/70 text-sm sm:text-base">
            Built and designed with 
            <span class="text-[#C9A96E]">love</span> by
            <a 
              href="https://x.com/iamteemotee" 
              target="_blank" 
              class="text-[#D4A574] hover:text-[#C9A96E] font-semibold transition-colors duration-300 hover:underline"
            >
              Timothy
            </a>
          </span>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const logoRef = ref(null)
const quoteRef = ref(null)
const socialRef = ref(null)
const navRef = ref(null)

const logoVisible = ref(false)
const quoteVisible = ref(false)
const socialVisible = ref(false)
const navVisible = ref(false)

const footerLinks = [
  { text: 'Our Story', href: '#our-story' },
  { text: 'Proposal', href: '#proposal' },
  { text: 'Memories', href: '#memories' },
  { text: 'Gift Us', href: '#gift-us' }
]

let observer = null

const observeElements = () => {
  const options = {
    threshold: 0.2,
    rootMargin: '0px 0px -50px 0px'
  }

  observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        if (entry.target === logoRef.value) logoVisible.value = true
        else if (entry.target === quoteRef.value) quoteVisible.value = true
        else if (entry.target === socialRef.value) socialVisible.value = true
        else if (entry.target === navRef.value) navVisible.value = true
      }
    })
  }, options)

  if (logoRef.value) observer.observe(logoRef.value)
  if (quoteRef.value) observer.observe(quoteRef.value)
  if (socialRef.value) observer.observe(socialRef.value)
  if (navRef.value) observer.observe(navRef.value)
}

onMounted(() => {
  observeElements()
})

onUnmounted(() => {
  if (observer) observer.disconnect()
})
</script>

<style scoped>
@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-15px); }
}

@keyframes float-delayed {
  0%, 100% { transform: translateY(0px) translateX(0px); }
  50% { transform: translateY(-10px) translateX(10px); }
}

.animate-float { animation: float 5s ease-in-out infinite; }
.animate-float-delayed { animation: float-delayed 7s ease-in-out infinite; }
</style>