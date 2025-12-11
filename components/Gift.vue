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

    <div class="container mx-auto max-w-6xl relative z-10">
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
         Your presence is truly the most treasured gift we could receive. Should you wish to bless us further, we have outlined a few options below:
        </p>
      </div>

      <!-- PART 1: Wishlist Gifts -->
      <div 
        ref="wishlistRef"
        class="mb-16 sm:mb-24 transition-all duration-[1600ms] ease-out"
        :class="{ 'opacity-0 translate-y-10': !wishlistVisible, 'opacity-100 translate-y-0': wishlistVisible }"
      >
        <div class="text-center mb-10">
          <div class="inline-flex items-center gap-3 mb-3">
            <div class="h-px w-12 bg-gradient-to-r from-transparent to-[#D4A574]"></div>
            <svg class="w-6 h-6 text-[#C9A96E]" fill="currentColor" viewBox="0 0 20 20">
              <path d="M3 1a1 1 0 000 2h1.22l.305 1.222a.997.997 0 00.01.042l1.358 5.43-.893.892C3.74 11.846 4.632 14 6.414 14H15a1 1 0 000-2H6.414l1-1H14a1 1 0 00.894-.553l3-6A1 1 0 0017 3H6.28l-.31-1.243A1 1 0 005 1H3zM16 16.5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zM6.5 18a1.5 1.5 0 100-3 1.5 1.5 0 000 3z" />
            </svg>
            <div class="h-px w-12 bg-gradient-to-l from-transparent to-[#C9A96E]"></div>
          </div>
          <h3 class="text-2xl sm:text-3xl font-bold text-[#3C2A21] mb-2">
            Wishlist Items
          </h3>
          <p class="text-sm sm:text-base text-[#3C2A21]/60">
            Items we'd love to receive as we start our new journey
          </p>
        </div>

        <!-- Wishlist Grid -->
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6">
          <div
            v-for="(item, index) in wishlistItems"
            :key="item.id"
            class="group relative bg-white rounded-2xl p-6 border border-[#D4A574]/20 shadow-md hover:shadow-xl transition-all duration-500 ease-out hover:-translate-y-1"
          >
            <!-- Category Icon -->
            <div class="w-12 h-12 rounded-full bg-gradient-to-br from-[#D4A574]/20 to-[#C9A96E]/20 flex items-center justify-center mb-4">
              <component :is="item.icon" class="w-6 h-6 text-[#C9A96E]" />
            </div>

            <!-- Item Details -->
            <div class="mb-4">
              <h4 class="text-lg font-bold text-[#3C2A21] mb-1">
                {{ item.name }}
              </h4>
              <p class="text-sm text-[#3C2A21]/60">
                {{ item.category }}
              </p>
            </div>

            <!-- Purchase Link -->
            <a
              :href="item.link"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-2 px-4 py-2 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] text-white text-sm font-medium rounded-full transition-all duration-500 ease-out hover:shadow-lg hover:shadow-[#C9A96E]/40 hover:scale-105 active:scale-95"
            >
              <span>View & Purchase</span>
              <svg class="w-4 h-4 transform group-hover:translate-x-1 transition-transform duration-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
              </svg>
            </a>

            <!-- Hover Effect Border -->
            <div class="absolute inset-0 border-2 border-[#C9A96E] rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-500 pointer-events-none"></div>
          </div>
        </div>
      </div>

      <!-- Divider -->
      <div class="flex items-center justify-center gap-4 my-12 sm:my-16">
        <div class="h-px w-20 sm:w-32 bg-gradient-to-r from-transparent via-[#D4A574] to-[#C9A96E]"></div>
        <div class="flex gap-2">
          <div class="w-2 h-2 rounded-full bg-[#D4A574]"></div>
          <div class="w-2 h-2 rounded-full bg-[#C9A96E]"></div>
          <div class="w-2 h-2 rounded-full bg-[#D4A574]"></div>
        </div>
        <div class="h-px w-20 sm:w-32 bg-gradient-to-l from-transparent via-[#C9A96E] to-[#D4A574]"></div>
      </div>

      <!-- PART 2: Monetary Gifts -->
      <div 
        ref="monetaryRef"
        class="transition-all duration-[1600ms] ease-out"
        :class="{ 'opacity-0 translate-y-10': !monetaryVisible, 'opacity-100 translate-y-0': monetaryVisible }"
      >
        <div class="text-center mb-10">
          
          <h3 class="text-2xl sm:text-3xl font-bold text-[#3C2A21] mb-2">
            Monetary Gifts 💝
          </h3>
        </div>

        <div class="max-w-4xl mx-auto">
          <div class="relative bg-gradient-to-br from-white to-[#FBF5EA] rounded-3xl shadow-2xl overflow-hidden border border-[#D4A574]/20">
            <!-- Decorative Top Border -->
            <div class="h-2 bg-gradient-to-r from-[#D4A574] via-[#C9A96E] to-[#D4A574]"></div>
            
            <!-- Content -->
            <div class="p-8 sm:p-12">
              <!-- Icon Header -->
              <div class="flex justify-center mb-8">
                <div class="w-20 h-20 rounded-full bg-gradient-to-br from-[#D4A574] to-[#C9A96E] flex items-center justify-center shadow-lg">
                  <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M4 4a2 2 0 00-2 2v1h16V6a2 2 0 00-2-2H4z" />
                    <path fill-rule="evenodd" d="M18 9H2v5a2 2 0 002 2h12a2 2 0 002-2V9zM4 13a1 1 0 011-1h1a1 1 0 110 2H5a1 1 0 01-1-1zm5-1a1 1 0 100 2h1a1 1 0 100-2H9z" clip-rule="evenodd" />
                  </svg>
                </div>
              </div>

              <!-- Bank Details Grid -->
              <div class="grid sm:grid-cols-3 gap-6 sm:gap-8 mb-8">
                <!-- Bank Name -->
                <div class="space-y-3">
                  <div class="flex items-center gap-2 text-sm font-medium text-[#D4A574] tracking-wider uppercase">
                    <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
                      <path d="M10.394 2.08a1 1 0 00-.788 0l-7 3a1 1 0 000 1.84L5.25 8.051a.999.999 0 01.356-.257l4-1.714a1 1 0 11.788 1.838L7.667 9.088l1.94.831a1 1 0 00.787 0l7-3a1 1 0 000-1.838l-7-3zM3.31 9.397L5 10.12v4.102a8.969 8.969 0 00-1.05-.174 1 1 0 01-.89-.89 11.115 11.115 0 01.25-3.762zM9.3 16.573A9.026 9.026 0 007 14.935v-3.957l1.818.78a3 3 0 002.364 0l5.508-2.361a11.026 11.026 0 01.25 3.762 1 1 0 01-.89.89 8.968 8.968 0 00-5.35 2.524 1 1 0 01-1.4 0zM6 18a1 1 0 001-1v-2.065a8.935 8.935 0 00-2-.712V17a1 1 0 001 1z" />
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
                      <p class="text-base sm:text-lg font-bold text-[#3C2A21]">Kuda</p>
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
                      Glory Oluwakemi Adekunle
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
                        2016128606
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
                  We are truly grateful.
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
import { ref, onMounted, onUnmounted, h } from 'vue'

const headerRef = ref(null)
const wishlistRef = ref(null)
const monetaryRef = ref(null)
const messageRef = ref(null)

const headerVisible = ref(false)
const wishlistVisible = ref(false)
const monetaryVisible = ref(false)
const messageVisible = ref(false)
const copied = ref(false)

let observer = null
let copyTimeout = null

// Wishlist Items with SVG icons
const wishlistItems = [
  {
    id: 1,
    name: 'Hisense 9kg Top Loader Automatic Washing Machine',
    category: 'Home Appliances',
    link: 'https://www.jumia.com.ng/hisense-9kg-top-loader-automatic-washing-machine-washspin-406364058.html?utm_medium=social&utm_campaign=pdpshare-apps',
    icon: (props) => h('svg', { ...props, fill: 'currentColor', viewBox: '0 0 20 20' }, [
      h('path', { 'fill-rule': 'evenodd', d: 'M6 2a2 2 0 00-2 2v12a2 2 0 002 2h8a2 2 0 002-2V4a2 2 0 00-2-2H6zm1 2a1 1 0 000 2h6a1 1 0 100-2H7zm6 7a1 1 0 011 1v3a1 1 0 11-2 0v-3a1 1 0 011-1zm-3 3a1 1 0 100 2h.01a1 1 0 100-2H10zm-4 1a1 1 0 011-1h.01a1 1 0 110 2H7a1 1 0 01-1-1zm1-4a1 1 0 100 2h.01a1 1 0 100-2H7zm2 1a1 1 0 011-1h.01a1 1 0 110 2H10a1 1 0 01-1-1zm4-4a1 1 0 100 2h.01a1 1 0 100-2H13zM9 9a1 1 0 011-1h.01a1 1 0 110 2H10a1 1 0 01-1-1zM7 8a1 1 0 000 2h.01a1 1 0 000-2H7z', 'clip-rule': 'evenodd' })
    ])
  },
  {
    id: 2,
    name: 'Silver Crest 8L Air Fryer Oven',
    category: 'Kitchen Appliances',
    link: 'https://www.jumia.com.ng/silver-crest-8l-glass-window-electric-digital-touch-screen-air-fryer-oven-363415559.html?utm_medium=social&utm_campaign=pdpshare-apps',
    icon: (props) => h('svg', { ...props, fill: 'currentColor', viewBox: '0 0 20 20' }, [
      h('path', { d: 'M3 12v3c0 1.657 3.134 3 7 3s7-1.343 7-3v-3c0 1.657-3.134 3-7 3s-7-1.343-7-3z' }),
      h('path', { d: 'M3 7v3c0 1.657 3.134 3 7 3s7-1.343 7-3V7c0 1.657-3.134 3-7 3S3 8.657 3 7z' }),
      h('path', { d: 'M17 5c0 1.657-3.134 3-7 3S3 6.657 3 5s3.134-3 7-3 7 1.343 7 3z' })
    ])
  },
  {
    id: 3,
    name: 'Haier Thermocool 146L Chest Freezer',
    category: 'Home Appliances',
    link: 'https://www.jumia.com.ng/haier-thermocool-146-litres-chest-freezer-htf-150-silver-3-years-warranty-110318763.html?utm_medium=social&utm_campaign=pdpshare-apps',
    icon: (props) => h('svg', { ...props, fill: 'currentColor', viewBox: '0 0 20 20' }, [
      h('path', { 'fill-rule': 'evenodd', d: 'M2.166 4.999A11.954 11.954 0 0010 1.944 11.954 11.954 0 0017.834 5c.11.65.166 1.32.166 2.001 0 5.225-3.34 9.67-8 11.317C5.34 16.67 2 12.225 2 7c0-.682.057-1.35.166-2.001zm11.541 3.708a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z', 'clip-rule': 'evenodd' })
    ])
  },
  {
    id: 4,
    name: 'Skyrun 3 Gas + 1 Electric Standing Cooker',
    category: 'Kitchen Appliances',
    link: 'https://www.jumia.com.ng/skyrun-3-burners1-electric-hotplate-gas-cooker-50x50-gcs-3g1ex-black.-370801436.html',
    icon: (props) => h('svg', { ...props, fill: 'currentColor', viewBox: '0 0 20 20' }, [
      h('path', { d: 'M10.394 2.08a1 1 0 00-.788 0l-7 3a1 1 0 000 1.84L5.25 8.051a.999.999 0 01.356-.257l4-1.714a1 1 0 11.788 1.838L7.667 9.088l1.94.831a1 1 0 00.787 0l7-3a1 1 0 000-1.838l-7-3zM3.31 9.397L5 10.12v4.102a8.969 8.969 0 00-1.05-.174 1 1 0 01-.89-.89 11.115 11.115 0 01.25-3.762zM9.3 16.573A9.026 9.026 0 007 14.935v-3.957l1.818.78a3 3 0 002.364 0l5.508-2.361a11.026 11.026 0 01.25 3.762 1 1 0 01-.89.89 8.968 8.968 0 00-5.35 2.524 1 1 0 01-1.4 0zM6 18a1 1 0 001-1v-2.065a8.935 8.935 0 00-2-.712V17a1 1 0 001 1z' })
    ])
  },
  {
    id: 5,
    name: 'Tornado Non-Stick Pots & Fry Pan Set',
    category: 'Kitchen Essentials',
    link: 'https://www.jumia.com.ng/high-quality-non-stick-cooking-pot-with-fry-pan-tornado-mpg3768073.html?utm_medium=social&utm_campaign=pdpshare-apps',
    icon: (props) => h('svg', { ...props, fill: 'currentColor', viewBox: '0 0 20 20' }, [
      h('path', { d: 'M3 12v3c0 1.657 3.134 3 7 3s7-1.343 7-3v-3c0 1.657-3.134 3-7 3s-7-1.343-7-3z' }),
      h('path', { d: 'M3 7v3c0 1.657 3.134 3 7 3s7-1.343 7-3V7c0 1.657-3.134 3-7 3S3 8.657 3 7z' }),
      h('path', { d: 'M17 5c0 1.657-3.134 3-7 3S3 6.657 3 5s3.134-3 7-3 7 1.343 7 3z' })
    ])
  },
  {
    id: 6,
    name: 'Couple Package - Spa Experience',
    category: 'Wellness & Relaxation',
    link: 'https://oriki.zenoti.com/webstoreNew/services/a9a42b3d-28ae-4f40-ac00-226e8eba1ad4',
    icon: (props) => h('svg', { ...props, fill: 'currentColor', viewBox: '0 0 20 20' }, [
      h('path', { 'fill-rule': 'evenodd', d: 'M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z', 'clip-rule': 'evenodd' })
    ])
  }
]

const copyAccountNumber = async () => {
  try {
    await navigator.clipboard.writeText('2016128606')
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
        } else if (entry.target === wishlistRef.value) {
          wishlistVisible.value = true
        } else if (entry.target === monetaryRef.value) {
          monetaryVisible.value = true
        } else if (entry.target === messageRef.value) {
          messageVisible.value = true
        }
      }
    })
  }, options)

  if (headerRef.value) observer.observe(headerRef.value)
  if (wishlistRef.value) observer.observe(wishlistRef.value)
  if (monetaryRef.value) observer.observe(monetaryRef.value)
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