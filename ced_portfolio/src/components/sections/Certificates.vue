<script setup lang="ts">
import lineFollowerCert from '../../assets/certificates/line_follower.png'

interface Certificate {
  title: string
  issuer: string
  date: string
  description: string
  image: string
}

const certificates: Certificate[] = [
  {
    title: 'Champion, Autonomous Line-Follower',
    issuer: 'IT Convention Robotics Competition',
    date: 'August 2026',
    description: 'Secured the championship title by designing, programming, and calibrating a custom autonomous robot utilizing advanced PID control loops and Kalman filtering for high-speed track navigation.',
    image: lineFollowerCert
  }
]
</script>

<template>
  <section class="animate-fade-in w-full flex flex-col">
    
    <div class="flex flex-col border-b border-gray-300 pb-8 mb-12">
      <span class="text-[10px] uppercase tracking-widest font-bold text-gray-400 mb-3 block">Milestones</span>
      <h2 class="text-4xl font-serif text-black">Certificates & Awards</h2>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <div
        v-for="cert in certificates"
        :key="cert.title"
        class="group flex flex-col border border-gray-200 bg-white hover:border-black transition-colors duration-300"
      >
        <div class="h-56 w-full bg-gray-50 border-b border-gray-200 overflow-hidden relative flex items-center justify-center p-4">
          <img
            :src="cert.image"
            :alt="cert.title"
            class="w-full h-full object-contain group-hover:grayscale-0 group-hover:opacity-100 group-hover:scale-105 transition-all duration-700 ease-out shadow-sm"
          />
        </div>

        <div class="flex flex-col p-6 md:p-8 flex-grow">
          <span class="text-[10px] font-bold uppercase tracking-widest text-gray-400 mb-2 block">
            {{ cert.date }}
          </span>
          
          <h3 class="text-xl font-serif text-black leading-snug mb-1">
            {{ cert.title }}
          </h3>
          
          <span class="text-[10px] font-bold tracking-widest uppercase text-black mb-4 block">
            {{ cert.issuer }}
          </span>
          
          <p class="text-[13px] text-gray-500 leading-relaxed mt-auto">
            {{ cert.description }}
          </p>
        </div>
      </div>
    </div>

  </section>
</template>

<style scoped>
.animate-fade-in {
  animation: fadeIn 0.4s ease-out;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

@media (prefers-reduced-motion: reduce) {
  .animate-fade-in { animation: none; }
}
</style>