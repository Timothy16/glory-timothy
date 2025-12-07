<template>
  <transition name="modal-fade">
    <div
      v-if="showModal"
      class="fixed inset-0 z-50 flex items-center justify-center bg-[#3C2A21]/90 backdrop-blur-sm"
    >
      <div
        class="text-center p-8 rounded-2xl border border-[#D4A574] bg-white/5 max-w-md mx-4 shadow-lg animate-fade-in"
      >
        <!-- Couple Names -->
        <h1 class="text-3xl md:text-4xl font-bold text-[#C9A96E] mb-2 tracking-wide">
          Glory & Timothy
        </h1>

        <!-- Wedding Hashtag with shimmer -->
        <p class="text-[#D4A574] mb-6 font-semibold tracking-wide shimmer-text">
          #GTLoveStory2025
        </p>

        <!-- Welcome Message -->
        <p class="text-[#D4A574] mb-8 italic">
          Welcome to our love page ❤️
        </p>

        <!-- Start Button -->
        <button
          @click="startExperience"
          class="px-8 py-3 bg-gradient-to-r from-[#D4A574] to-[#C9A96E] hover:from-[#C9A96E] hover:to-[#D4A574] text-white font-semibold rounded-full shadow-lg transition-all duration-500 transform hover:scale-105 active:scale-95"
        >
          Start
        </button>
      </div>
    </div>
  </transition>
</template>

<script setup>
import { ref } from 'vue'

const emit = defineEmits(['start'])
const showModal = ref(true)

const startExperience = () => {
  showModal.value = false
  setTimeout(() => emit('start'), 700) // match fade duration
}
</script>

<style scoped>
/* Entrance Animation */
@keyframes fade-in {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
.animate-fade-in {
  animation: fade-in 0.8s ease-out;
}

/* Exit Transition */
.modal-fade-leave-active {
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.modal-fade-leave-to {
  opacity: 0;
  transform: scale(0.95);
}

/* Soft gold shimmer for hashtag */
@keyframes shimmer {
  0% {
    text-shadow: 0 0 5px #c9a96e, 0 0 10px #d4a574, 0 0 20px #c9a96e;
  }
  50% {
    text-shadow: 0 0 15px #d4a574, 0 0 25px #c9a96e, 0 0 35px #d4a574;
  }
  100% {
    text-shadow: 0 0 5px #c9a96e, 0 0 10px #d4a574, 0 0 20px #c9a96e;
  }
}
.shimmer-text {
  animation: shimmer 3s ease-in-out infinite alternate;
}
</style>
