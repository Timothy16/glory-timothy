<template>
  <section 
    id="gift-us" 
    class="relative py-20 sm:py-32 px-4 sm:px-6 overflow-hidden bg-gradient-to-br from-[#FBF5EA] via-white to-[#FBF5EA]"
  >
    <!-- Decorative Background Elements -->
    <div class="absolute top-10 right-10 w-40 h-40 bg-[#D4A574]/10 rounded-full blur-3xl animate-float"></div>
    <div class="absolute bottom-20 left-10 w-48 h-48 bg-[#C9A96E]/10 rounded-full blur-3xl animate-float-delayed"></div>
    
    <!-- Decorative Pattern -->
    <div class="absolute inset-0 opacity-5">
      <div class="absolute top-1/4 left-1/4 w-32 h-32 border-2 border-[#D4A574] rounded-full"></div>
      <div class="absolute bottom-1/3 right-1/3 w-24 h-24 border-2 border-[#C9A96E] rounded-full"></div>
    </div>

    <div class="container mx-auto max-w-5xl relative z-10">
      <!-- Section Header -->
      <div 
        ref="headerRef"
        class="text-center mb-16 sm:mb-20 transition-all duration-[1800ms] ease-out"
        :class="{ 'opacity-0 translate-y-10': !headerVisible, 'opacity-100 translate-y-0': headerVisible }"
      >
        <div class="inline-flex items-center gap-3 mb-6 px-6 py-3 bg-white rounded-full shadow-lg border border-[#D4A574]/20">
          <svg class="w-6 h-6 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
            <path d="M5 4a2 2 0 00-2 2v6H1.5a.5.5 0 000 1H3v1a2 2 0 002 2h10a2 2 0 002-2v-1h1.5a.5.5 0 000-1H17V6a2 2 0 00-2-2H5zm10 8H5V6h10v6z" />
          </svg>
          <span class="text-sm font-medium text-[#3C2A21] tracking-wider uppercase">Bless Us</span>
        </div>
        
        <h2 class="text-4xl sm:text-5xl md:text-6xl font-bold text-[#3C2A21] mb-4 tracking-wide">
          Gift Us
        </h2>
        <p class="text-base sm:text-lg text-[#3C2A21]/70 max-w-2xl mx-auto leading-relaxed">
          Your presence is the greatest gift, but if you wish to bless us with a monetary gift, we'll be deeply grateful
        </p>
      </div>

      <!-- Gift Card -->
      <div 
        ref="cardRef"
        class="transition-all duration-[1600ms] ease-out"
        :class="{ 'opacity-0 scale-95': !cardVisible, 'opacity-100 scale-100': cardVisible }"
      >
        <div class="relative bg-gradient-to-br from-white to-[#FBF5EA] rounded-3xl shadow-2xl overflow-hidden border border-[#D4A574]/20">
          <!-- Decorative Top Border -->
          <div class="h-2 bg-gradient-to-r from-[#D4A574] via-[#C9A96E] to-[#D4A574]"></div>
          
          <!-- Content -->
          <div class="p-8 sm:p-12">
            <!-- Icon Header -->
            <div class="flex justify-center mb-8">
              <div class="w-20 h-20 rounded-full bg-gradient-to-br from-[#D4A574] to-[#C9A96E] flex items-center justify-center shadow-lg">
                <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
                </svg>
              </div>
            </div>

            <h3 class="text-2xl sm:text-3xl font-bold text-[#3C2A21] text-center mb-8">
              Monetary Gifts 💝
            </h3>

            <!-- Bank Details Grid -->
            <div class="grid sm:grid-cols-3 gap-6 sm:gap-8 mb-8">
              <!-- Bank Name -->
              <div class="space-y-3">
                <div class="flex items-center gap-2 text-sm font-medium text-[#D4A574] tracking-wider uppercase">
                  <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M4 4a2 2 0 00-2 2v1h16V6a2 2 0 00-2-2H4z" />
                    <path fill-rule="evenodd" d="M18 9H2v5a2 2 0 002 2h12a2 2 0 002-2V9zM4 13a1 1 0 011-1h1a1 1 0 110 2H5a1 1 0 01-1-1zm5-1a1 1 0 100 2h1a1 1 0 100-2H9z" clip-rule="evenodd" />
                  </svg>
                  <span>Bank Name</span>
                </div>
                <div class="flex items-center gap-3 bg-white rounded-xl p-4 border border-[#D4A574]/20 shadow-sm">
                  <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#D4A574]/20 to-[#C9A96E]/20 flex items-center justify-center flex-shrink-0">
                    <svg class="w-5 h-5 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
                      <path d="M10.394 2.08a1 1 0 00-.788 0l-7 3a1 1 0 000 1.84L5.25 8.051a.999.999 0 01.356-.257l4-1.714a1 1 0 11.788 1.838L7.667 9.088l1.94.831a1 1 0 00.787 0l7-3a1 1 0 000-1.838l-7-3zM3.31 9.397L5 10.12v4.102a8.969 8.969 0 00-1.05-.174 1 1 0 01-.89-.89 11.115 11.115 0 01.25-3.762zM9.3 16.573A9.026 9.026 0 007 14.935v-3.957l1.818.78a3 3 0 002.364 0l5.508-2.361a11.026 11.026 0 01.25 3.762 1 1 0 01-.89.89 8.968 8.968 0 00-5.35 2.524 1 1 0 01-1.4 0zM6 18a1 1 0 001-1v-2.065a8.935 8.935 0 00-2-.712V17a1 1 0 001 1z" />
                    </svg>
                  </div>
                  <div>
                    <p class="text-lg sm:text-xl font-bold text-[#3C2A21]">United Bank of Africa</p>
                  </div>
                </div>
              </div>

              <!-- Account Name -->
              <div class="space-y-3">
                <div class="flex items-center gap-2 text-sm font-medium text-[#D4A574] tracking-wider uppercase">
                  <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd" />
                  </svg>
                  <span>Account Name</span>
                </div>
                <div class="bg-white rounded-xl p-4 border border-[#D4A574]/20 shadow-sm">
                  <p class="text-base sm:text-lg font-bold text-[#3C2A21] break-words">
                    Afolabi Timothy
                  </p>
                </div>
              </div>

              <!-- Account Number -->
              <div class="space-y-3">
                <div class="flex items-center gap-2 text-sm font-medium text-[#D4A574] tracking-wider uppercase">
                  <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-12a1 1 0 10-2 0v4a1 1 0 00.293.707l2.828 2.829a1 1 0 101.415-1.415L11 9.586V6z" clip-rule="evenodd" />
                  </svg>
                  <span>Account Number</span>
                </div>
                <div class="bg-white rounded-xl p-4 border border-[#D4A574]/20 shadow-sm">
                  <div class="flex items-center justify-between gap-3">
                    <p class="text-xl sm:text-2xl font-bold text-[#3C2A21] tracking-wider">
                      2068461254
                    </p>
                    <button
                      @click="copyAccountNumber"
                      class="group flex-shrink-0 p-2 hover:bg-[#D4A574]/10 rounded-lg transition-all duration-300 hover:scale-110 active:scale-95"
                      :aria-label="copied ? 'Copied!' : 'Copy account number'"
                      :title="copied ? 'Copied!' : 'Copy account number'"
                    >
                      <svg 
                        v-if="!copied"
                        class="w-5 h-5 text-[#3C2A21] group-hover:text-[#C9A96E] transition-colors duration-300" 
                        fill="currentColor" 
                        viewBox="0 0 20 20"
                      >
                        <path d="M8 3a1 1 0 011-1h2a1 1 0 110 2H9a1 1 0 01-1-1z" />
                        <path d="M6 3a2 2 0 00-2 2v11a2 2 0 002 2h8a2 2 0 002-2V5a2 2 0 00-2-2 3 3 0 01-3 3H9a3 3 0 01-3-3z" />
                      </svg>
                      <svg 
                        v-else
                        class="w-5 h-5 text-[#C9A96E]" 
                        fill="currentColor" 
                        viewBox="0 0 20 20"
                      >
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                      </svg>
                    </button>
                  </div>
                </div>
              </div>
            </div>

            <!-- Copy Notification -->
            <transition
              enter-active-class="transition-all duration-300 ease-out"
              enter-from-class="opacity-0 translate-y-2"
              enter-to-class="opacity-100 translate-y-0"
              leave-active-class="transition-all duration-200 ease-in"
              leave-from-class="opacity-100 translate-y-0"
              leave-to-class="opacity-0 translate-y-2"
            >
              <div 
                v-if="copied"
                class="text-center py-3 px-6 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] text-white rounded-full text-sm font-medium shadow-lg mb-6"
              >
                ✓ Account number copied to clipboard!
              </div>
            </transition>

            <!-- Decorative Divider -->
            <div class="flex items-center justify-center gap-4 my-8">
              <div class="h-px w-20 bg-gradient-to-r from-transparent to-[#D4A574]"></div>
              <svg class="w-6 h-6 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
              </svg>
              <div class="h-px w-20 bg-gradient-to-l from-transparent to-[#C9A96E]"></div>
            </div>

            <!-- Thank You Message -->
            <div class="text-center space-y-4">
              <p class="text-base sm:text-lg italic text-[#3C2A21]/70 leading-relaxed" style="font-family: Georgia, serif;">
                Thank you for your love and generosity
              </p>
              <div class="flex items-center justify-center gap-2">
                <div class="w-2 h-2 rounded-full bg-[#D4A574] animate-pulse"></div>
                <div class="w-2 h-2 rounded-full bg-[#C9A96E] animate-pulse" style="animation-delay: 0.2s;"></div>
                <div class="w-2 h-2 rounded-full bg-[#D4A574] animate-pulse" style="animation-delay: 0.4s;"></div>
              </div>
            </div>
          </div>

          <!-- Decorative Bottom Corner -->
          <div class="absolute bottom-0 right-0 w-32 h-32 bg-gradient-to-tl from-[#D4A574]/10 to-transparent rounded-tl-full"></div>
        </div>
      </div>

      <!-- Additional Message -->
      <div 
        ref="messageRef"
        class="mt-12 text-center transition-all duration-[1800ms] ease-out"
        :class="{ 'opacity-0 translate-y-10': !messageVisible, 'opacity-100 translate-y-0': messageVisible }"
      >
        <p class="text-sm sm:text-base text-[#3C2A21]/60 max-w-2xl mx-auto leading-relaxed">
          Your prayers, presence, and well wishes are truly what matter most to us. Any gift is simply an added blessing to our special day.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const headerRef = ref(null)
const cardRef = ref(null)
const messageRef = ref(null)

const headerVisible = ref(false)
const cardVisible = ref(false)
const messageVisible = ref(false)
const copied = ref(false)

let observer = null
let copyTimeout = null

const copyAccountNumber = async () => {
  try {
    await navigator.clipboard.writeText('5050296404')
    copied.value = true
    
    if (copyTimeout) {
      clearTimeout(copyTimeout)
    }
    
    copyTimeout = setTimeout(() => {
      copied.value = false
    }, 3000)
  } catch (err) {
    console.error('Failed to copy:', err)
  }
}

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
        } else if (entry.target === cardRef.value) {
          cardVisible.value = true
        } else if (entry.target === messageRef.value) {
          messageVisible.value = true
        }
      }
    })
  }, options)

  if (headerRef.value) observer.observe(headerRef.value)
  if (cardRef.value) observer.observe(cardRef.value)
  if (messageRef.value) observer.observe(messageRef.value)
}

onMounted(() => {
  observeElements()
})

onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
  if (copyTimeout) {
    clearTimeout(copyTimeout)
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