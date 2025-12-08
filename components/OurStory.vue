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
      <div class="grid md:grid-cols-2 gap-8 sm:gap-12 mb-12 items-start">
        <!-- First Story Card - Tim's Story (UPDATED TEXT) -->
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
                <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" />
                </svg>
              </div>
              <div>
                <p class="text-sm text-[#D4A574] font-medium tracking-wider uppercase">His Story</p>
                <p class="text-xs text-[#3C2A21]/60">Tim's Perspective</p>
              </div>
            </div>
            
            <!-- Story Content -->
            <div class="space-y-4">
              <!-- Preview (first paragraph - always visible) -->
              <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                On a beautiful Saturday morning, I saw a damsel in a wine-coloured dress doing her Chief Bridesmaid duty, while I was doing my Agbada groomsmen duty. I noticed the joy and happiness on her face. 
              </p>
              
              <!-- Expanded Content - Fixed 400px Height & Scrollable -->
              <div 
                class="overflow-hidden transition-all duration-500 ease-in-out"
                :class="{ 'h-0': !card1Expanded, 'h-[400px]': card1Expanded }"
              >
                <div class="h-full overflow-y-auto scrollbar-thin scrollbar-thumb-[#D4A574]/30 scrollbar-track-transparent pt-4 pr-2">
                  <div class="space-y-4">
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                     I knew it was her elder sister's wedding and that she should be happy, but what I saw went beyond that moment. Instantly, something stirred in me, I knew I would have a part to play in her life, though I couldn’t figure out exactly how at that moment.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      Days, weeks, and months went by, and the only thing I kept seeing were her pictures on her sister’s husband’s status who happened to be a friend and a brother. I kept telling myself, “This is the one.” I decided to learn more about her, and I was told different things; God-fearing, kind, intelligent, full of joy etc. I just said to myself, “I’ve found the one my heart desires.”
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      They spoke with her on my behalf, and we got connected. From our very first call, it felt as if we had known each other for years. The conversation flowed effortlessly, and from day one, I kept telling her, “I will be here for a very long time.”
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      Our conversations grew stronger; every late-night call became a moment I looked forward to. When she requested a meeting, I was nervous because she had never seen me in person before, though I had seen her. But I was welcomed with a warm hug that I haven't and will never forgot. Till today, I still feel the warmth and peace that came with that embrace.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      Days turned into months, and months turned into years. Our love grew deeper, our connection strengthened, and I knew without a doubt that she is the woman I wanted to spend the rest of my life with.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      As time went on, our conversations deepened, I found clarity in the little moments; the laughter we shared, the values we aligned on, the prayers we prayed, and the quiet consistency of our bond. From that point on, the journey has been nothing short of beautiful.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      Her love reflects everything I ever hoped for, gentle in nature, strong in depth, steady in commitment, and full of understanding. She loves intentionally, with peace, sacrifice, grace, and sincerity.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      I am getting married to an extraordinary woman, thoughtful, compassionate, and beautiful inside and out. The one whose presence brings a sense of home, and the one God had written into my story long before I ever realized it. Together, this marks the beginning of our forever. ❤
                    </p>
                  </div>
                </div>
              </div>
              
              <!-- See More/Less Button -->
              <button
                @click="card1Expanded = !card1Expanded"
                class="mt-6 text-[#D4A574] hover:text-[#C9A96E] font-medium text-sm flex items-center gap-2 transition-colors duration-300"
              >
                {{ card1Expanded ? 'See Less' : 'See More' }}
                <svg 
                  class="w-4 h-4 transition-transform duration-300" 
                  :class="{ 'rotate-180': card1Expanded }"
                  fill="none" 
                  stroke="currentColor" 
                  viewBox="0 0 24 24"
                >
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                </svg>
              </button>
            </div>
          </div>
          
          <!-- Hover Gradient Effect -->
          <div class="absolute inset-0 bg-gradient-to-br from-[#D4A574]/5 to-[#C9A96E]/5 rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700"></div>
        </div>

        <!-- Second Story Card - Glory's Story (unchanged) -->
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
                <p class="text-sm text-[#C9A96E] font-medium tracking-wider uppercase">Her Story</p>
                <p class="text-xs text-[#3C2A21]/60">Glory's Perspective</p>
              </div>
            </div>
            
            <!-- Story Content -->
            <div class="space-y-4">
              <!-- Preview (always visible) -->
              <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                If someone had told me I would meet my husband the way I did, I honestly would have laughed. Our story started quietly, through family long before I even knew anything was happening.
              </p>
              
              <!-- Expanded Content - Fixed Height & Scrollable -->
              <div 
                class="overflow-hidden transition-all duration-500 ease-in-out"
                :class="{ 'h-0': !card2Expanded, 'h-[400px]': card2Expanded }"
              >
                <div class="h-full overflow-y-auto scrollbar-thin scrollbar-thumb-[#C9A96E]/30 scrollbar-track-transparent pt-4 pr-2">
                  <div class="space-y-4">
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      It started all as a joke until it became real. I have always been loud about my kind of man and God used my very own people to orchestrate this divine meeting.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      I was on a visit in Ibadan with my sister when a conversation about my relationship started and as usual, the response was, no one for now. It seems like my sister and her husband were waiting for me to say that when they said, they had someone they would love me to be friends with.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      At first, it seems like the usual whining. But it kept getting serious, they spoke about him with such seriousness, warmth and certainty. Who is this person? I asked. Apparently, he was one of the groomsmen at their wedding while I was the Chief Bridesmaid. So, while I was going about my duties, someone was observing me with interest and admiration. Lol!
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      I asked some questions about him, and the responses were positive. Then, I gave the go-ahead to share my contact with him. October 16, 2022 (A whole 15 months after), he reached out and from that conversation, it felt easy, like I had known him for a long time. We shared similar experiences, common belief, same values, common conversations and spiritual grounding. Talking to him felt natural.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      Still, I needed to meet him physically. He had seen me before, but I had never truly seen him. He travelled down and from a distance, I could tell a thousand thing were going through his mind, but I saw something different in that instance. I could read him. I could hear what his heart was saying. I could read everything, his intention, his sincerity, his quiet strength. In that moment, I was settled in my spirit. I gave him a warm welcome hug as a sign of "You're welcome here" so he could stop overthinking. Lol!
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      From that day, our conversations grew deeper, softer, better. He asked me out, not for something casual, but for something serious, something meaningful, something that could lead to marriage. I gave him a response he wasn't expecting. And that shook him. For a few days, the weight of my response sat between us.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      But we continued being friends. Months passed, conversations continued, and somewhere between the laughter, the shared values, the prayers, and the gentle consistency, my heart found its peace. About six months later, I had my conviction, and I said yes.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      And since then, it has been the most beautiful journey. His love is everything I prayed for; gentle, kind, deep, soft, steady, and understanding. He didn't come loudly, he came with calmness, intention, and grace.
                    </p>
                    <p class="text-base sm:text-lg leading-relaxed text-[#3C2A21]/80">
                      I'm getting married to the most intentional, kind, and handsome man, the one whose love is home, the one God wrote into my story long before I knew it. This is how our journey to forever began. ❤
                    </p>
                  </div>
                </div>
              </div>
              
              <!-- See More/Less Button -->
              <button
                @click="card2Expanded = !card2Expanded"
                class="mt-6 text-[#C9A96E] hover:text-[#D4A574] font-medium text-sm flex items-center gap-2 transition-colors duration-300"
              >
                {{ card2Expanded ? 'See Less' : 'See More' }}
                <svg 
                  class="w-4 h-4 transition-transform duration-300" 
                  :class="{ 'rotate-180': card2Expanded }"
                  fill="none" 
                  stroke="currentColor" 
                  viewBox="0 0 24 24"
                >
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                </svg>
              </button>
            </div>
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
        class="text-center max-w-8xl mx-auto transition-all duration-1000"
        :class="{ 'opacity-0 translate-y-10': !quoteVisible, 'opacity-100 translate-y-0': quoteVisible }"
      >
        <div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-16">
          <p class="text-2xl sm:text-3xl md:text-4xl font-light text-[#3C2A21] italic leading-relaxed">
            "He came softly, but his sincerity echoed loudly in my spirit."
            <span class="block md:text-right mt-3 text-base sm:text-lg not-italic font-medium text-[#3C2A21]">
              — Glory
            </span>
          </p>
          <p class="text-2xl sm:text-3xl md:text-4xl font-light text-[#D4A574] italic leading-relaxed">
            "She listened with her heart, and her presence answered me completely."
            <span class="block md:text-right mt-3 text-base sm:text-lg not-italic font-medium text-[#D4A574]">
              — Tim
            </span>
          </p>
        </div>
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

const card1Expanded = ref(false)
const card2Expanded = ref(false)

let observer = null

const observeElements = () => {
  const options = { threshold: 0.2, rootMargin: '0px 0px -100px 0px' }

  observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        if (entry.target === headerRef.value) headerVisible.value = true
        else if (entry.target === card1Ref.value) card1Visible.value = true
        else if (entry.target === card2Ref.value) card2Visible.value = true
        else if (entry.target === timelineRef.value) timelineVisible.value = true
        else if (entry.target === quoteRef.value) quoteVisible.value = true
      }
    })
  }, options)

  if (headerRef.value) observer.observe(headerRef.value)
  if (card1Ref.value) observer.observe(card1Ref.value)
  if (card2Ref.value) observer.observe(card2Ref.value)
  if (timelineRef.value) observer.observe(timelineRef.value)
  if (quoteRef.value) observer.observe(quoteRef.value)
}

onMounted(() => observeElements())
onUnmounted(() => observer?.disconnect())
</script>

<style scoped>
@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-20px); }
}
@keyframes float-delayed {
  0%, 100% { transform: translateY(0px) translateX(0px); }
  50% { transform: translateY(-15px) translateX(10px); }
}
.animate-float { animation: float 6s ease-in-out infinite; }
.animate-float-delayed { animation: float-delayed 8s ease-in-out infinite; }

.scrollbar-thin::-webkit-scrollbar { width: 6px; }
.scrollbar-thin::-webkit-scrollbar-track { background: transparent; }
.scrollbar-thin::-webkit-scrollbar-thumb { background-color: currentColor; border-radius: 3px; opacity: 0.3; }
.scrollbar-thin::-webkit-scrollbar-thumb:hover { opacity: 0.5; }
</style>