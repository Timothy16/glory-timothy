<template>
  <div>
    <SeoHead />
    <Navbar />
    <Hero />
    <OurStory />
    <TheProposal />
    <Memories />
    <Gift />
    <Footer />

    <!-- Welcome Modal -->
    <WelcomeModal @start="handleStart" />

    <!-- Background Music -->
    <audio
      ref="backgroundMusic"
      src="/for-life.mp3"
      loop
      playsinline
    ></audio>

    <!-- Floating Play/Pause Button (Coffee Brown) -->
    <transition name="fade">
      <button
        v-if="showMusicControls"
        @click="toggleMusic"
        :class="[
          'fixed bottom-6 right-6 z-40 flex items-center justify-center w-14 h-14 bg-[#3C2A21]/90 backdrop-blur-md rounded-full shadow-xl hover:shadow-2xl transition-all duration-300 hover:scale-110 group border border-[#D4A574]/20',
          { 'animate-pulse-ring': isPlaying }
        ]"
        aria-label="Toggle background music"
      >
        <!-- Play Icon -->
        <svg
          v-if="!isPlaying"
          class="w-6 h-6 text-[#C9A96E] group-hover:text-[#D4A574] transition-colors"
          fill="currentColor"
          viewBox="0 0 24 24"
        >
          <path d="M8 5v14l11-7L8 5z" />
        </svg>

        <!-- Pause Icon -->
        <svg
          v-else
          class="w-6 h-6 text-[#C9A96E] group-hover:text-[#D4A574] transition-colors"
          fill="currentColor"
          viewBox="0 0 24 24"
        >
          <path d="M6 19h4V5H6v14zm8-14v14h4V5h-4z" />
        </svg>
      </button>
    </transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useHead } from '@unhead/vue'
import Navbar from '~/components/Navbar.vue'
import Hero from '~/components/Hero.vue'
import OurStory from '~/components/OurStory.vue'
import TheProposal from '~/components/TheProposal.vue'
import Memories from '~/components/Memories.vue'
import Gift from '~/components/Gift.vue'
import Footer from '~/components/Footer.vue'
import WelcomeModal from '~/components/WelcomeModal.vue'

// SEO Head Component
const SeoHead = defineComponent({
  name: 'SeoHead',
  setup() {
    useHead({
      title: 'Glory and Timothy | Our Love Story, Proposal & Wedding Gift Registry',
      meta: [
        {
          name: 'description',
          content:
            'Join Glory and Timothy as we celebrate our journey from friendship to forever. Explore our love story, magical proposal, cherished memories, and contribute to our future through our gift registry. December 20, 2025.'
        },
        {
          name: 'keywords',
          content:
            'Glory Timothy wedding, love story, proposal, wedding gift registry, Nigerian couple, @iamteemotee, engagement'
        },
        { name: 'author', content: 'Glory and Timothy' },
        { name: 'robots', content: 'index, follow' },
        { property: 'og:title', content: 'Glory and Timothy | Our Love Story & Wedding Celebration' },
        {
          property: 'og:description',
          content:
            'From the first spark to "Yes!" – relive our journey and be part of our next chapter. Gift us your love and blessings.'
        },
        { property: 'og:type', content: 'website' },
        { property: 'og:url', content: 'https://glory-timothy.vercel.app' },
        { property: 'og:image', content: 'https://glory-timothy.vercel.app/favicon.png' },
        {
          property: 'og:image:alt',
          content:
            'Glory and Timothy smiling together during golden hour engagement photoshoot in Lagos, Nigeria'
        },
        { property: 'og:image:width', content: '1200' },
        { property: 'og:image:height', content: '630' },
        { property: 'og:site_name', content: 'Glory and Timothy Wedding' },
        { property: 'og:locale', content: 'en_NG' },
        { name: 'twitter:card', content: 'summary_large_image' },
        { name: 'twitter:site', content: '@iamteemotee' },
        { name: 'twitter:creator', content: '@iamteemotee' },
        { name: 'twitter:title', content: 'Glory and Timothy | Our Love Story & Wedding Gift Registry' },
        {
          name: 'twitter:description',
          content:
            'Celebrate with us! Explore our proposal, memories, and help build our future home with your gift.'
        },
        { name: 'twitter:image', content: 'https://glory-timothy.vercel.app/favicon.png' },
        {
          name: 'twitter:image:alt',
          content: 'Glory and Timothy holding hands at sunset, Lagos skyline in background – Nigerian couple engagement'
        },
        { rel: 'canonical', href: 'https://glory-timothy.vercel.app/' },
        { name: 'geo.region', content: 'NG' },
        { name: 'geo.placename', content: 'Lagos' }
      ],
      link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.png' }]
    })
  },
  render: () => null
})

// Audio & UI State
const backgroundMusic = ref(null)
const isPlaying = ref(false)
const showMusicControls = ref(false)

const handleStart = () => {
  showMusicControls.value = true // Show button
  if (backgroundMusic.value) {
    backgroundMusic.value.volume = 0
    backgroundMusic.value.play().catch((err) => {
      console.warn('Music play failed:', err)
    })

    // Smooth fade-in
    let vol = 0
    const fadeIn = setInterval(() => {
      if (vol < 0.7) {
        vol += 0.05
        backgroundMusic.value.volume = vol
      } else {
        clearInterval(fadeIn)
        isPlaying.value = true // Music is now playing
      }
    }, 200)
  }
}

const toggleMusic = () => {
  if (!backgroundMusic.value) return

  if (isPlaying.value) {
    backgroundMusic.value.pause()
  } else {
    backgroundMusic.value.play().catch(() => {})
  }
  isPlaying.value = !isPlaying.value
}
</script>

<style scoped>
audio {
  display: none;
}

/* Button fade-in */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease, transform 0.4s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(10px);
}

/* Pulse animation when music is playing */
@keyframes pulse {
  0% {
    box-shadow: 0 0 0 0 rgba(212, 165, 116, 0.4);
  }
  70% {
    box-shadow: 0 0 0 12px rgba(212, 165, 116, 0);
  }
  100% {
    box-shadow: 0 0 0 0 rgba(212, 165, 116, 0);
  }
}

.animate-pulse-ring {
  animation: pulse 2s infinite;
}
</style>