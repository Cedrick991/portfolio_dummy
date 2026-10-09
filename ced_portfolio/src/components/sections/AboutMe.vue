<script setup lang="ts">
import pfp from '../../assets/pfp.jpg'
import coverFace from '../../assets/cover_face.jpg'

const pfpImage = pfp
const coverImage = coverFace 

interface Milestone {
  period: string
  title: string
  description: string
}

interface Principle {
  title: string
  description: string
}

const principles: Principle[] = [
  {
    title: 'Plan before I build',
    description: 'I work through the approach step by step and check that it is compatible and right before committing to it, instead of building on assumptions.'
  },
  {
    title: 'Performance first, design close behind',
    description: 'I care about both, but if I have to choose, I lean toward performance: a fast, reliable system before a polished one.'
  },
  {
    title: "Verify, don't guess",
    description: 'When something breaks, I confirm the actual cause instead of assuming it. Debugging across both hardware and software comes fast because of that habit.'
  },
  {
    title: "AI as a development tool",
    description: "I use AI to accelerate development without outsourcing the thinking. Architecture, tradeoffs, and implementation stay in my hands."
  },
  {
    title: "Aesthetic versatility through iteration",
    description: "Whether mapping out a stark minimalist interface, a chaotic maximalist scene, or nostalgic retro pixel art, I build interactive demos to prove the concept. Using tools like Three.js and spatial animation, I ensure the visual language actively serves the experience."
  }
]

const milestones: Milestone[] = [
  {
    period: 'Childhood',
    title: 'Self-taught, before any formal class',
    description: 'Picked up Python, JavaScript, and C++ on my own, and took apart electronics just to understand how they worked, then put them back together.'
  },
  {
    period: 'Year 1',
    title: 'First language: C',
    description: 'Learned programming fundamentals through C: control flow, functions, and how code actually runs underneath.'
  },
  {
    period: 'Year 1 – 2',
    title: 'Data structures and algorithms in C++',
    description: 'Moved into C++ for data structures, algorithms, and how to structure code that scales past a single file.'
  },
  {
    period: 'Year 2',
    title: 'Object-oriented programming in Java',
    description: 'Learned OOP properly through Java: classes, inheritance, and designing around objects instead of just procedures.'
  },
  {
    period: 'Electives',
    title: 'Python for data analysis, Vue and Django for full-stack work',
    description: 'Elective coursework added Python for data analysis, then Vue on the frontend paired with Django on the backend.'
  },
  {
    period: 'Software Design',
    title: 'Vet Clinic, solo full-stack and DevOps',
    description: 'Built a veterinary appointment and records platform alone, end to end: frontend, backend, database, and deployment.'
  },
  {
    period: 'On-the-Job Training',
    title: 'CedLMS, first production system',
    description: 'Built a learning management system during OJT with no hosting budget: first time with React, TypeScript, Express, and MongoDB, and first time handling real infrastructure, security testing, and AI integration end to end.'
  },
  {
    period: 'Creative Tech',
    title: 'Games, 3D, and Spatial Animation',
    description: 'Expanded beyond traditional UIs into game development and interactive 3D. Building demos that explore diverse aesthetics—from retro pixel art to maximalism—using tools like Three.js, Godot, and custom spatial animations.'
  },
  {
    period: 'Now',
    title: 'Software, hardware, and AI',
    description: 'Working across full-stack web, embedded hardware, and mobile, and using AI to move faster without skipping the fundamentals.'
  }
]
</script>

<template>
  <div class="animate-fade-in flex flex-col gap-10">
    
    <div class="flex flex-col md:flex-row-reverse md:items-start justify-between gap-8 border-b border-gray-100 pb-10">
      
      <div class="relative group self-center md:self-start shrink-0 h-44 w-44 md:h-48 md:w-48 select-none">
        <div class="absolute -inset-2 rounded-2xl border-2 border-dashed border-gray-200 group-hover:border-black group-hover:scale-105 transition-all duration-500 ease-out pointer-events-none"></div>
        <div class="absolute -inset-3 border-t-2 border-l-2 border-gray-300 w-4 h-4 rounded-tl-lg group-hover:-translate-x-1 group-hover:-translate-y-1 transition-transform duration-500 ease-out"></div>
        <div class="absolute -inset-3 border-b-2 border-r-2 border-gray-300 w-4 h-4 bottom-0 right-0 rounded-br-lg group-hover:translate-x-1 group-hover:translate-y-1 transition-transform duration-500 ease-out"></div>

        <div class="w-full h-full rounded-xl overflow-hidden border border-gray-200 bg-gray-50 flex items-center justify-center relative shadow-sm transition-transform duration-500 group-hover:scale-[1.02] group-hover:shadow-md">
          
          <div class="absolute inset-0 bg-grid-pattern opacity-10 group-hover:opacity-15 transition-opacity duration-500"></div>

          <div v-if="!pfpImage" class="absolute inset-0 flex flex-col items-center justify-center text-gray-400 group-hover:text-black transition-colors duration-500">
            <span class="absolute top-2 left-3 text-[7px] font-mono tracking-widest text-gray-300 group-hover:text-gray-400 select-none">CED_01 // PFP</span>
            <span class="absolute bottom-2 right-3 text-[7px] font-mono tracking-widest text-gray-300 group-hover:text-gray-400 select-none">[45° 110]</span>

            <svg class="w-20 h-20 md:w-24 md:h-24 opacity-60 group-hover:opacity-100 transition-all duration-500 group-hover:scale-105" viewBox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="1.25">
              <circle cx="50" cy="40" r="18" stroke-dasharray="2 3" class="opacity-40" />
              <circle cx="50" cy="50" r="44" stroke-dasharray="3 4" class="opacity-20 animate-[spin_60s_linear_infinite]" />
              <path d="M50 25 C43 25 38 30 38 37 C38 41 40 45 44 47 C43 51 40 54 36 56 C30 59 26 67 26 75 L74 75 C74 67 70 59 64 56 C60 54 57 51 56 47 C60 45 62 41 62 37 C62 30 57 25 50 25 Z" stroke-linejoin="round" />
              <path d="M30 65 L40 59 L44 59" class="opacity-50 group-hover:opacity-100 transition-opacity" />
              <circle cx="30" cy="65" r="1.5" fill="currentColor" class="opacity-50 group-hover:opacity-100" />
              <path d="M70 65 L60 59 L56 59" class="opacity-50 group-hover:opacity-100 transition-opacity" />
              <circle cx="70" cy="65" r="1.5" fill="currentColor" class="opacity-50 group-hover:opacity-100" />
              <circle cx="50" cy="37" r="1" fill="currentColor" class="opacity-60" />
              <circle cx="53" cy="37" r="1" fill="currentColor" class="opacity-60" />
              <path d="M50 31 L50 21" stroke-dasharray="1 1.5" class="opacity-40" />
            </svg>
            <span class="text-[9px] font-bold tracking-widest uppercase mt-1 opacity-40 group-hover:opacity-100">PLACEHOLDER</span>
          </div>

            <div v-else class="w-full h-full relative">
              <img 
                :src="pfpImage" 
                alt="Cedrick profile photo" 
                class="absolute inset-0 w-full h-full object-cover grayscale opacity-90 group-hover:opacity-100 transition-all duration-700 ease-out" 
              />
              <img 
                v-if="coverImage"
                :src="coverImage" 
                alt="Covered face overlay" 
                class="absolute inset-0 w-full h-full object-cover grayscale opacity-0 group-hover:opacity-100 transition-opacity duration-500 ease-out" 
              />
            </div>

        </div>
      </div>

      <div class="flex flex-col gap-4 flex-grow max-w-2xl">
        <span class="text-[10px] uppercase tracking-widest font-bold text-gray-400 block">Background</span>
        <h2 class="text-4xl font-serif text-black">About Me</h2>
        <p class="text-[15px] leading-relaxed text-gray-500">
          I've been building things since I was a kid, teaching myself Python, JavaScript, and C++ before I ever took a class, and taking apart electronics just to see how they worked. That turned into a formal path through C, C++, Java, and full-stack web development during my Computer Engineering studies, and then into real production work: hosting, security, and AI integration on projects with real constraints. Beyond pure logic, I build games and craft digital experiences across a wide spectrum of visual languages—from stark minimalism and intense maximalism to retro pixel art. I bring these aesthetics to life through interactive demos, leveraging spatial animation and 3D rendering with tools like Three.js. I move quickly across both software and hardware, and I pick up new tools fast.
        </p>
      </div>

    </div>

    <ol class="relative flex flex-col gap-8 border-l border-gray-200 pl-6">
      <li v-for="milestone in milestones" :key="milestone.title" class="relative">
        <span class="absolute -left-[1.65rem] top-1.5 h-2.5 w-2.5 rounded-full bg-black" aria-hidden="true"></span>
        <span class="text-[10px] font-bold uppercase tracking-widest text-gray-400">{{ milestone.period }}</span>
        <h3 class="mt-1 font-serif text-lg text-black">{{ milestone.title }}</h3>
        <p class="mt-1 max-w-2xl text-[14px] leading-relaxed text-gray-500">{{ milestone.description }}</p>
      </li>
    </ol>

    <div class="flex flex-col gap-4">
      <span class="text-[10px] uppercase tracking-widest font-bold text-gray-400 block">How I Build</span>
      <div class="grid grid-cols-1 md:grid-cols-2 border-t border-l border-gray-200">
        <div
          v-for="principle in principles"
          :key="principle.title"
          class="flex flex-col gap-2 p-6 border-r border-b border-gray-200 bg-white hover:bg-gray-50 transition-colors duration-300"
        >
          <h3 class="font-serif text-lg text-black">{{ principle.title }}</h3>
          <p class="text-[14px] leading-relaxed text-gray-500">{{ principle.description }}</p>
        </div>
      </div>
    </div>
  </div>
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

.bg-grid-pattern {
  background-image: 
    radial-gradient(circle, #e5e7eb 1.5px, transparent 1.5px),
    linear-gradient(to right, #f3f4f6 1px, transparent 1px),
    linear-gradient(to bottom, #f3f4f6 1px, transparent 1px);
  background-size: 14px 14px;
}
</style>