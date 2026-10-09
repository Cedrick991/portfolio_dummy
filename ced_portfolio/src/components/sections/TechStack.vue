<script setup lang="ts">
import cppLogo from '../../assets/images/cpp_logo.webp'
import djangoLogo from '../../assets/images/django.webp'
import dockerLogo from '../../assets/images/docker.webp'
import godotLogo from '../../assets/images/godot.webp'
import javaLogo from '../../assets/images/java.webp'
import jsLogo from '../../assets/images/javascript.webp'
import mongoLogo from '../../assets/images/mongodb.webp'
import nodeLogo from '../../assets/images/node_js.webp'
import postgresLogo from '../../assets/images/postgres.webp'
import prismaLogo from '../../assets/images/prisma.webp'
import rabbitmqLogo from '../../assets/images/rabbit_mq.webp'
import raspiLogo from '../../assets/images/raspberry_pi.webp'
import reactLogo from '../../assets/images/react_logo.webp'
import reactNativeLogo from '../../assets/images/react_native.webp'
import redisLogo from '../../assets/images/redis.webp'
import renderLogo from '../../assets/images/render.webp'
import rustLogo from '../../assets/images/rust.webp'
import tsLogo from '../../assets/images/typescript.webp'
import vercelLogo from '../../assets/images/vercel.webp'
import htmlLogo from '../../assets/images/html-5.webp'
import cssLogo from '../../assets/images/css.webp'
import tailwindLogo from '../../assets/images/tailwindcss.webp'
import vueLogo from '../../assets/images/vue.webp'
import androidStudioLogo from '../../assets/images/android_studio.webp'
import javaFxLogo from '../../assets/images/javaFX.webp'
import kotlinLogo from '../../assets/images/kotlin.webp'
import springBootLogo from '../../assets/images/spring_boot.webp'
import websocketsLogo from '../../assets/images/websockets.webp'
import firebaseLogo from '../../assets/images/firebase.webp'
import tauriLogo from '../../assets/images/tauri.webp'
import dosboxLogo from '../../assets/images/dosbox.webp'
import arduinoLogo from '../../assets/images/arduino_ide.webp'
import matlabLogo from '../../assets/images/matlab.webp'
import phpLogo from '../../assets/images/php.webp'
import vsCodeLogo from '../../assets/images/vs_code.webp'
import cLogo from '../../assets/images/c.webp'
import visualStudioLogo from '../../assets/images/visual_studio.webp'
import chatGptLogo from '../../assets/images/chatgpt.webp'
import claudeLogo from '../../assets/images/claude.webp'
import flaskLogo from '../../assets/images/flask.webp'
import geminiLogo from '../../assets/images/gemini.webp'
import deepseekLogo from '../../assets/images/deepseek.webp'
import gradleLogo from '../../assets/images/gradle.webp'
import kimiLogo from '../../assets/images/kimi.webp'
import linuxLogo from '../../assets/images/linux.webp'
import ollamaLogo from '../../assets/images/ollama.webp'
import openRouterLogo from '../../assets/images/open_router.webp'
import qwenLogo from '../../assets/images/qwen.webp'
import webrtcLogo from '../../assets/images/web_rtc.webp'
import blenderLogo from '../../assets/images/blender.webp'
import expressLogo from '../../assets/images/expressjs.png'

interface Skill {
  name: string
  img: string
}

interface TechCategory {
  title: string
  description: string
  skills: Skill[]
}

const techCategories: TechCategory[] = [
  {
    title: 'Languages',
    description: 'The languages behind firmware, systems code, web apps, and mobile apps.',
    skills: [
      { name: 'JavaScript', img: jsLogo },
      { name: 'TypeScript', img: tsLogo },
      { name: 'Rust', img: rustLogo },
      { name: 'C++', img: cppLogo },
      { name: 'C', img: cLogo },
      { name: 'Java', img: javaLogo },
      { name: 'Kotlin', img: kotlinLogo },
      { name: 'PHP', img: phpLogo }
    ]
  },
  {
    title: 'Embedded & Hardware',
    description: 'Microcontroller and single-board platforms for sensing, control, and monitoring.',
    skills: [
      { name: 'Arduino', img: arduinoLogo },
      { name: 'Raspberry Pi', img: raspiLogo }
    ]
  },
  {
    title: 'Web Frontend',
    description: 'Building reactive user interfaces for the browser.',
    skills: [
      { name: 'HTML5', img: htmlLogo },
      { name: 'CSS3', img: cssLogo },
      { name: 'React', img: reactLogo },
      { name: 'Vue.js', img: vueLogo },
      { name: 'Tailwind CSS', img: tailwindLogo }
    ]
  },
  {
    title: 'Mobile & Desktop',
    description: 'Cross-platform and native apps for Android and the desktop.',
    skills: [
      { name: 'React Native', img: reactNativeLogo },
      { name: 'Tauri', img: tauriLogo },
      { name: 'JavaFX', img: javaFxLogo },
      { name: 'Android Studio', img: androidStudioLogo },
      { name: 'Gradle', img: gradleLogo }
    ]
  },
  {
    title: 'Backend & Realtime',
    description: 'Developing scalable APIs and real-time networking.',
    skills: [
      { name: 'Node.js', img: nodeLogo },
      { name: 'Express.js', img: expressLogo },
      { name: 'Django', img: djangoLogo },
      { name: 'Flask', img: flaskLogo },
      { name: 'Spring Boot', img: springBootLogo },
      { name: 'WebSockets', img: websocketsLogo },
      { name: 'WebRTC', img: webrtcLogo }
    ]
  },
  {
    title: 'Database & BaaS',
    description: 'Structuring, storing, syncing, and caching critical application data.',
    skills: [
      { name: 'PostgreSQL', img: postgresLogo },
      { name: 'MongoDB', img: mongoLogo },
      { name: 'Redis', img: redisLogo },
      { name: 'Prisma', img: prismaLogo },
      { name: 'Firebase', img: firebaseLogo }
    ]
  },
  {
    title: 'DevOps & OS',
    description: 'Operating systems, containerization, message brokering, and cloud hosting.',
    skills: [
      { name: 'Linux', img: linuxLogo },
      { name: 'Docker', img: dockerLogo },
      { name: 'RabbitMQ', img: rabbitmqLogo },
      { name: 'Vercel', img: vercelLogo },
      { name: 'Render', img: renderLogo }
    ]
  },
  {
    title: 'Simulation, Game & 3D',
    description: 'Numerical simulation, game engines, 3D modeling, and system emulation.',
    skills: [
      { name: 'MATLAB', img: matlabLogo },
      { name: 'Godot', img: godotLogo },
      { name: 'Blender', img: blenderLogo },
      { name: 'DOSBox', img: dosboxLogo }
    ]
  },
  {
    title: 'Development Tools & AI',
    description: 'IDEs, coding environments, LLMs, and AI APIs for rapid development.',
    skills: [
      { name: 'VS Code', img: vsCodeLogo },
      { name: 'Visual Studio', img: visualStudioLogo },
      { name: 'ChatGPT', img: chatGptLogo },
      { name: 'Claude', img: claudeLogo },
      { name: 'Gemini', img: geminiLogo },
      { name: 'DeepSeek', img: deepseekLogo },
      { name: 'Qwen', img: qwenLogo },
      { name: 'Kimi', img: kimiLogo },
      { name: 'Ollama', img: ollamaLogo },
      { name: 'OpenRouter', img: openRouterLogo }
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