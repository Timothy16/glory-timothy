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
  </div>
</template>

<script setup>
import { useHead } from '@unhead/vue';
import Navbar from '~/components/Navbar.vue';
import Hero from '~/components/Hero.vue';
import OurStory from '~/components/OurStory.vue';
import TheProposal from '~/components/TheProposal.vue';
import Memories from '~/components/Memories.vue';
import Gift from '~/components/Gift.vue';
import Footer from '~/components/Footer.vue';

// SEO Head Component (using Unhead for Nuxt 3+)
const SeoHead = defineComponent({
  name: 'SeoHead',
  setup() {
    useHead({
      // Core SEO Meta Tags
      title: 'Glory and Timothy | Our Love Story, Proposal & Wedding Gift Registry',
      meta: [
        { name: 'description', content: 'Join Glory and Timothy as we celebrate our journey from friendship to forever. Explore our love story, magical proposal, cherished memories, and contribute to our future through our gift registry. December 20, 2025.' },
        { name: 'keywords', content: 'Glory Timothy wedding, love story, proposal, wedding gift registry, Nigerian couple, @iamteemotee, engagement' },
        { name: 'author', content: 'Glory and Timothy' },
        { name: 'robots', content: 'index, follow' },

        // Open Graph / Facebook
        { property: 'og:title', content: 'Glory and Timothy | Our Love Story & Wedding Celebration' },
        { property: 'og:description', content: 'From the first spark to "Yes!" – relive our journey and be part of our next chapter. Gift us your love and blessings.' },
        { property: 'og:type', content: 'website' },
        { property: 'og:url', content: 'https://temiandtee.com' }, // Update with actual domain
        { property: 'og:image', content: 'https://temiandtee.com/favicon.png' },
        { property: 'og:image:alt', content: 'Glory and Timothy smiling together during golden hour engagement photoshoot in Lagos, Nigeria' },
        { property: 'og:image:width', content: '1200' },
        { property: 'og:image:height', content: '630' },
        { property: 'og:site_name', content: 'Glory and Timothy Wedding' },
        { property: 'og:locale', content: 'en_NG' },

        // Twitter Card
        { name: 'twitter:card', content: 'summary_large_image' },
        { name: 'twitter:site', content: '@iamteemotee' },
        { name: 'twitter:creator', content: '@iamteemotee' },
        { name: 'twitter:title', content: 'Glory and Timothy | Our Love Story & Wedding Gift Registry' },
        { name: 'twitter:description', content: 'Celebrate with us! Explore our proposal, memories, and help build our future home with your gift.' },
        { name: 'twitter:image', content: 'https://temiandtee.com/favicon.png' },
        { name: 'twitter:image:alt', content: 'Glory and Timothy holding hands at sunset, Lagos skyline in background – Nigerian couple engagement' },

        // Canonical URL
        { rel: 'canonical', href: 'https://temiandtee.com' },

        // Additional Structured Data Hint (JSON-LD can be added separately if needed)
        { name: 'geo.region', content: 'NG' },
        { name: 'geo.placename', content: 'Lagos' }
      ],
      link: [
        { rel: 'icon', type: 'image/x-icon', href: '/favicon.png' }
      ]
    });
  },
  render: () => null // Head-only component
});
</script>

<style scoped>
/* Optional: Add global styles if needed */
</style>