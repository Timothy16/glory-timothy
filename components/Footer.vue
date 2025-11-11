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

        <!-- Social Links / Contact (Optional) -->
        <div 
          ref="socialRef"
          class="flex justify-center gap-6 sm:gap-8 mb-10 transition-all duration-[1800ms] ease-out"
          :class="{ 'opacity-0 translate-y-10': !socialVisible, 'opacity-100 translate-y-0': socialVisible }"
        >
          <!-- Instagram -->
          <a
            href="#"
            class="group w-12 h-12 sm:w-14 sm:h-14 rounded-full bg-white/10 backdrop-blur-sm flex items-center justify-center transition-all duration-500 hover:bg-gradient-to-br hover:from-[#D4A574] hover:to-[#C9A96E] hover:scale-110 hover:shadow-lg hover:shadow-[#C9A96E]/50"
            aria-label="Instagram"
          >
            <svg class="w-5 h-5 sm:w-6 sm:h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
            </svg>
          </a>

          <!-- Twitter/X -->
          <a
            href="#"
            class="group w-12 h-12 sm:w-14 sm:h-14 rounded-full bg-white/10 backdrop-blur-sm flex items-center justify-center transition-all duration-500 hover:bg-gradient-to-br hover:from-[#D4A574] hover:to-[#C9A96E] hover:scale-110 hover:shadow-lg hover:shadow-[#C9A96E]/50"
            aria-label="Twitter"
          >
            <svg class="w-5 h-5 sm:w-6 sm:h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
              <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
            </svg>
          </a>

          <!-- Facebook -->
          <a
            href="#"
            class="group w-12 h-12 sm:w-14 sm:h-14 rounded-full bg-white/10 backdrop-blur-sm flex items-center justify-center transition-all duration-500 hover:bg-gradient-to-br hover:from-[#D4A574] hover:to-[#C9A96E] hover:scale-110 hover:shadow-lg hover:shadow-[#C9A96E]/50"
            aria-label="Facebook"
          >
            <svg class="w-5 h-5 sm:w-6 sm:h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
              <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
            </svg>
          </a>

          <!-- Email -->
          <a
            href="mailto:wedding@example.com"
            class="group w-12 h-12 sm:w-14 sm:h-14 rounded-full bg-white/10 backdrop-blur-sm flex items-center justify-center transition-all duration-500 hover:bg-gradient-to-br hover:from-[#D4A574] hover:to-[#C9A96E] hover:scale-110 hover:shadow-lg hover:shadow-[#C9A96E]/50"
            aria-label="Email"
          >
            <svg class="w-5 h-5 sm:w-6 sm:h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
          </a>
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

   <!-- Copyright Bar -->
<div class="bg-[#2a1f18] py-6 px-4 sm:px-6">
  <div 
    ref="copyrightRef"
    class="container mx-auto max-w-6xl transition-all duration-[1800ms] ease-out"
    :class="{ 'opacity-0': !copyrightVisible, 'opacity-100': copyrightVisible }"
  >
    <div class="flex flex-col sm:flex-row items-center justify-center gap-3 sm:gap-4 flex-wrap text-center">
      <div class="flex items-center gap-2">
        <svg class="w-5 h-5 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
          <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM8.736 6.979C9.208 6.193 9.696 6 10 6c.304 0 .792.193 1.264.979a1 1 0 001.715-1.029C12.279 4.784 11.232 4 10 4s-2.279.784-2.979 1.95c-.285.475-.507 1-.67 1.55H6a1 1 0 000 2h.013a9.358 9.358 0 000 1H6a1 1 0 100 2h.351c.163.55.385 1.075.67 1.55C7.721 15.216 8.768 16 10 16s2.279-.784 2.979-1.95a1 1 0 10-1.715-1.029c-.472.786-.96.979-1.264.979-.304 0-.792-.193-1.264-.979a4.265 4.265 0 01-.264-.521H10a1 1 0 100-2H8.017a7.36 7.36 0 010-1H10a1 1 0 100-2H8.472c.08-.185.167-.36.264-.521z" clip-rule="evenodd" />
        </svg>
        <span class="font-semibold text-white/70 text-sm sm:text-base">2025</span>
      </div>
      
      <span class="hidden sm:block w-1 h-1 rounded-full bg-white/30"></span>
      
      <span class="text-white/70 text-sm sm:text-base">
        Built and designed with 
        <span class="text-[#C9A96E]">love</span> by 
        <a 
          href="https://x.com/iamteemotee" 
          target="_blank" 
          class="text-[#D4A574] hover:text-[#C9A96E] font-semibold transition-colors duration-300 hover:underline ml-1"
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
const copyrightRef = ref(null)

const logoVisible = ref(false)
const quoteVisible = ref(false)
const socialVisible = ref(false)
const navVisible = ref(false)
const copyrightVisible = ref(false)

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
        if (entry.target === logoRef.value) {
          logoVisible.value = true
        } else if (entry.target === quoteRef.value) {
          quoteVisible.value = true
        } else if (entry.target === socialRef.value) {
          socialVisible.value = true
        } else if (entry.target === navRef.value) {
          navVisible.value = true
        } else if (entry.target === copyrightRef.value) {
          copyrightVisible.value = true
        }
      }
    })
  }, options)

  if (logoRef.value) observer.observe(logoRef.value)
  if (quoteRef.value) observer.observe(quoteRef.value)
  if (socialRef.value) observer.observe(socialRef.value)
  if (navRef.value) observer.observe(navRef.value)
  if (copyrightRef.value) observer.observe(copyrightRef.value)
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
    transform: translateY(-15px);
  }
}

@keyframes float-delayed {
  0%, 100% {
    transform: translateY(0px) translateX(0px);
  }
  50% {
    transform: translateY(-10px) translateX(10px);
  }
}

.animate-float {
  animation: float 5s ease-in-out infinite;
}

.animate-float-delayed {
  animation: float-delayed 7s ease-in-out infinite;
}
</style>