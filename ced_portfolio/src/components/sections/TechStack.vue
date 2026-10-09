<script setup lang="ts">
interface Skill {
  name: string
  img: string
}

interface TechCategory {
  title: string
  description: string
  skills: Skill[]
}

// instead of mag import dami eto nalang
const logoFiles = import.meta.glob('../../assets/images/*.{webp,png}', {
  eager: true,
  import: 'default'
}) as Record<string, string>

const t = (name: string, file?: string): Skill => {
  if (!file) return { name, img: '' }
  const foundImage =
    logoFiles[`../../assets/images/${file}.webp`] ||
    logoFiles[`../../assets/images/${file}.png`]
  return { name, img: foundImage ? (foundImage as string) : '' }
}

const techCategories: TechCategory[] = [
  {
    title: 'Languages',
    description: 'The languages behind firmware, systems code, web apps, and mobile apps.',
    skills: [
      t('JavaScript', 'javascript'),
      t('TypeScript', 'typescript'),
      t('Rust', 'rust'),
      t('C++', 'cpp_logo'),
      t('C', 'c'),
      t('Java', 'java'),
      t('Kotlin', 'kotlin'),
      t('PHP', 'php')
    ]
  },
  {
    title: 'Embedded & Hardware',
    description: 'Microcontroller and single-board platforms for sensing, control, and monitoring.',
    skills: [
      t('Arduino', 'arduino_ide'),
      t('Raspberry Pi', 'raspberry_pi')
    ]
  },
  {
    title: 'Web Frontend',
    description: 'Building reactive user interfaces for the browser.',
    skills: [
      t('HTML5', 'html-5'),
      t('CSS3', 'css'),
      t('React', 'react_logo'),
      t('Vue.js', 'vue'),
      t('Tailwind CSS', 'tailwindcss')
    ]
  },
  {
    title: 'Mobile & Desktop',
    description: 'Cross-platform and native apps for Android and the desktop.',
    skills: [
      t('React Native', 'react_native'),
      t('Tauri', 'tauri'),
      t('JavaFX', 'javaFX'),
      t('Android Studio', 'android_studio'),
      t('Gradle', 'gradle')
    ]
  },
  {
    title: 'Backend & Realtime',
    description: 'Developing scalable APIs and real-time networking.',
    skills: [
      t('Node.js', 'node_js'),
      t('Express.js', 'expressjs'),
      t('Django', 'django'),
      t('Flask', 'flask'),
      t('Spring Boot', 'spring_boot'),
      t('WebSockets', 'websockets'),
      t('WebRTC', 'web_rtc')
    ]
  },
  {
    title: 'Database & BaaS',
    description: 'Structuring, storing, syncing, and caching critical application data.',
    skills: [
      t('PostgreSQL', 'postgres'),
      t('MongoDB', 'mongodb'),
      t('Redis', 'redis'),
      t('Prisma', 'prisma'),
      t('Firebase', 'firebase')
    ]
  },
  {
    title: 'DevOps & OS',
    description: 'Operating systems, containerization, message brokering, and cloud hosting.',
    skills: [
      t('Linux', 'linux'),
      t('Docker', 'docker'),
      t('RabbitMQ', 'rabbit_mq'),
      t('Vercel', 'vercel'),
      t('Render', 'render')
    ]
  },
  {
    title: 'Simulation, Game & 3D',
    description: 'Numerical simulation, game engines, 3D modeling, and system emulation.',
    skills: [
      t('MATLAB', 'matlab'),
      t('Godot', 'godot'),
      t('Blender', 'blender'),
      t('DOSBox', 'dosbox')
    ]
  },
  {
    title: 'Development Tools & AI',
    description: 'IDEs, coding environments, LLMs, and AI APIs for rapid development.',
    skills: [
      t('VS Code', 'vs_code'),
      t('Visual Studio', 'visual_studio'),
      t('ChatGPT', 'chatgpt'),
      t('Claude', 'claude'),
      t('Gemini', 'gemini'),
      t('DeepSeek', 'deepseek'),
      t('Qwen', 'qwen'),
      t('Kimi', 'kimi'),
      t('Ollama', 'ollama'),
      t('OpenRouter', 'open_router')
    ]
  }
]
</script>

<template>
  <section class="animate-fade-in w-full flex flex-col">
    <div class="flex flex-col border-b border-gray-300 pb-6 mb-12">
      <span class="text-[10px] uppercase tracking-widest font-bold text-gray-500 mb-3 block">Technical Arsenal</span>
      <h2 class="text-4xl font-serif text-black">Tech Stack</h2>
    </div>

    <div class="flex flex-col gap-12">
      <div
        v-for="(category, index) in techCategories"
        :key="category.title"
        class="grid grid-cols-1 md:grid-cols-[260px_1fr] gap-8 border-b border-gray-200 pb-12 last:border-0 last:pb-0"
      >
        <div class="flex flex-col gap-3">
          <h3 class="text-[10px] font-bold tracking-widest uppercase text-black">
            {{ String(index + 1).padStart(2, '0') }} / {{ category.title }}
          </h3>
          <p class="text-xs text-gray-500 leading-relaxed max-w-[220px]">
            {{ category.description }}
          </p>
        </div>

        <ul class="flex flex-wrap gap-x-6 gap-y-8 items-start">
          <li
            v-for="skill in category.skills"
            :key="skill.name"
            class="group flex flex-col items-center gap-4 w-20"
          >
            <div class="h-10 flex items-center justify-center">
              <img
                v-if="skill.img"
                :src="skill.img"
                alt=""
                loading="lazy"
                class="skill-logo max-h-full max-w-full object-contain"
              />
            </div>
            <span class="text-[10px] font-bold tracking-widest uppercase text-gray-500 group-hover:text-black transition-colors duration-500 motion-reduce:transition-none text-center">
              {{ skill.name }}
            </span>
          </li>
        </ul>
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
  .animate-fade-in {
    animation: none;
  }
}
</style>