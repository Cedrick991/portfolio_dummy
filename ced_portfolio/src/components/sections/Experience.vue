<script setup lang="ts">
import { ref, computed } from 'vue'

const logoFiles = import.meta.glob('../../assets/images/*.{webp,png}', {
  eager: true,
  import: 'default'
}) as Record<string, string>

const t = (name: string, file?: string): Tech => {
  if (!file) return { name, logo: undefined }
  const foundImage = logoFiles[`../../assets/images/${file}.webp`] || logoFiles[`../../assets/images/${file}.png`]
  return { name, logo: foundImage ? (foundImage as string) : undefined }
}

const tech = {
  react: t('React', 'react_logo'),
  reactNative: t('React Native', 'react_native'),
  expo: t('Expo', 'expo'),
  typescript: t('TypeScript', 'typescript'),
  node: t('Node.js', 'node_js'),
  express: t('Express', 'expressjs'),
  websockets: t('WebSockets', 'websockets'),
  webrtc: t('WebRTC', 'web_rtc'),
  opencv: t('OpenCV', 'opencv'),
  ocr: t('OCR', 'ocr'),
  groq: t('Groq API', 'groq'),
  rust: t('Rust', 'rust'),
  tauri: t('Tauri', 'tauri'),
  llama: t('llama.cpp', 'llama_cpp'),
  cpp: t('C++', 'cpp_logo'),
  arduino: t('Arduino', 'arduino_ide'),
  esp32: t('ESP32', 'esp32'),
  freertos: t('FreeRTOS', 'freertos'),
  mpu: t('MPU6050'),
  atm90: t('ATM90E36'),
  avrdude: t('avrdude'),
  pi: t('Raspberry Pi', 'raspberry_pi'),
  osm: t('OpenStreetMap', 'openstreetmap'),
  mediamtx: t('MediaMTX'),
  ml: t('Machine Learning'),
  python: t('Python', 'python'),
  java: t('Java', 'java'),
  c: t('C', 'c'),
  django: t('Django', 'django'),
  kubernetes: t('Kubernetes', 'kubernetes'),
  rabbitmq: t('RabbitMQ', 'rabbit_mq'),
  render: t('Render', 'render'),
  php: t('PHP', 'php'),
  laravel: t('Laravel', 'laravel'),
  mysql: t('MySQL', 'Mysql'),
  pcb: t('PCB Design'),
  cad: t('3D Design')
}

interface Tech {
  name: string
  logo?: string
}

interface CollectionItem {
  title: string
  note: string
  url: string
}

interface Project {
  id: string
  title: string
  role?: string
  year?: string
  category: string[]
  tech: Tech[]
  description?: string[]
  collection?: CollectionItem[]
  links: { repo?: string; demo?: string }
}

const experienceData: Project[] = [
  {
    id: 'cedlms',
    title: 'CedLMS',
    role: 'Full-Stack Developer, DevOps & AI Engineer',
    year: '2026',
    category: ['Web', 'AI'],
    tech: [
      tech.react, tech.typescript, tech.express, tech.node, tech.python,
      tech.django, tech.websockets, tech.opencv, tech.ocr, tech.groq,
      tech.render, tech.rabbitmq, tech.kubernetes
    ],
    links: { repo: 'https://github.com/Cedrick991/CedLMS-Learning-Management-System-NodeJs' },
    description: [
      "Architected and deployed a comprehensive learning management system with zero hosting budget, securing it against vulnerabilities through manual penetration testing.",
      "Engineered an automated exam grading pipeline that processes poorly-lit handwritten scans using OpenCV, extracts text via OCR, and interprets answers contextually using the Groq API. Additionally, built a provider-agnostic AI chatbot that allows students to plug in their own local or cloud AI models for tailored educational assistance.",
      "Designed a resilient backend architecture queued by RabbitMQ to absorb traffic spikes, with multiple instances orchestrated via Kubernetes to ensure high availability for real-time WebSockets and video features."
    ]
  },
  {
    id: 'sinagtala',
    title: 'Sinagtala Rescue Drone',
    role: 'Mobile Developer',
    year: '2026',
    category: ['Mobile'],
    tech: [tech.reactNative, tech.expo, tech.typescript, tech.osm, tech.pi, tech.mediamtx],
    links: { repo: 'https://github.com/Cedrick991/drone_viewApp' },
    description: [
      "Built an Android flight HUD designed specifically for emergency responders operating in disaster zones with zero cellular connectivity.",
      "Engineered an offline OpenStreetMap tile downloading system to maintain spatial awareness. Integrated local telemetry, live camera feeds, and thermal imaging directly from the drone's Raspberry Pi hotspot over MediaMTX, allowing operators to easily switch views without internet reliance."
    ]
  },
  {
    id: 'esp32-fc',
    title: 'Drone Flight Controller',
    role: 'Firmware Developer',
    year: '2026',
    category: ['Embedded', 'Hardware'],
    tech: [tech.esp32, tech.freertos, tech.cpp, tech.mpu],
    links: { repo: 'https://github.com/Cedrick991/esp32_flightcontoller' },
    description: [
      "Wrote custom quadcopter flight controller firmware from scratch on an ESP32, integrating its own Betaflight interface.",
      "Utilized FreeRTOS to assign time-critical control loops (IMU reading, PID) to core 1, while isolating the web server on core 0, preventing network lag from crashing the drone. Diagnosed and resolved severe hardware brownouts under motor load by optimizing the power path."
    ]
  },
  {
    id: 'pid-line',
    title: 'Line-Follower',
    role: 'Robotics Programmer & Hardware Designer',
    year: '2026',
    category: ['Embedded', 'Hardware'],
    tech: [tech.arduino, tech.cpp, tech.pcb, tech.cad],
    links: { repo: 'https://github.com/Cedrick991/line_follower_code' },
    description: [
      "Led the mechanical, electrical, and software design of a high-speed autonomous robot, ultimately winning the Champion title at the ITE Convention robotics competition.",
      "Transitioned from a fragile breadboard prototype to a custom-designed PCB and 3D-printed chassis. Programmed an advanced PID control loop smoothed by a Kalman filter, allowing the robot to navigate tight corners at maximum speed without derailing."
    ]
  },
  {
    id: 'ced-ai',
    title: 'Ced AI',
    role: 'Systems Developer',
    year: '2026',
    category: ['Desktop', 'AI'],
    tech: [tech.tauri, tech.rust, tech.react, tech.llama],
    links: { repo: 'https://github.com/Cedrick991/ced_Ai' },
    description: [
      "Developed a modular, locally-hosted desktop AI assistant using Tauri 2 and React 19, powered by a high-performance Rust backend.",
      "Structured the application as a multi-crate Rust workspace to cleanly separate the orchestrator, model-router, and tooling. Solved complex Windows compilation issues with llama-cpp-sys to successfully enable offline model inference directly on the user's machine."
    ]
  },
  {
    id: 'rustotics',
    title: 'Rustotics',
    role: 'Systems Engineer',
    year: '2026',
    category: ['Desktop', 'Hardware'],
    tech: [tech.rust, tech.cpp],
    links: { repo: 'https://github.com/Cedrick991/Rustotics' },
    description: [
      "Built an Arduino IDE alternative dedicated to writing and compiling microcontrollers using Rust.",
      "Engineered a custom serial bridge in Rust to bypass avrdude timeouts, meticulously managing baud rates and DTR/RTS toggling. This direct serial access achieved a 99.8% successful flash rate and significantly faster upload times."
    ]
  },
  {
    id: 'vet-clinic',
    title: 'Vet Clinic Portal',
    role: 'Full-Stack Developer & DevOps',
    year: '2025',
    category: ['Web'],
    tech: [tech.php, tech.laravel, tech.mysql],
    links: { repo: 'https://github.com/Cedrick991/vetclinic' },
    description: [
      "Solely designed, developed, and deployed a veterinary management platform handling appointment scheduling and sensitive patient records.",
      "Built the relational MySQL database and PHP/Laravel backend to support automated, timely reminders for critical animal vaccinations and follow-up care."
    ]
  },
  {
    id: 'smart-trash',
    title: 'Smart Trash Bin',
    role: 'Developer',
    year: '2026',
    category: ['Embedded', 'AI'],
    tech: [tech.ml, tech.cpp],
    links: { repo: 'https://github.com/Cedrick991/smartTrash' },
    description: [
      "Created an automated waste sorting system capable of distinguishing between plastic and paper without relying on cloud APIs.",
      "Trained and deployed a local machine learning model to edge hardware, allowing the bin to accurately sort waste completely offline."
    ]
  },
  {
    id: 'plant-watering',
    title: 'Automated Plant Watering',
    role: 'Developer',
    year: '2025',
    category: ['Embedded', 'Hardware'],
    tech: [tech.esp32, tech.cpp],
    links: { repo: 'https://github.com/Cedrick991/Diligan_Automated_Water_Plants' },
    description: [
      "Developed a dynamic IoT irrigation system using an ESP32 that replaces inefficient timer-based watering.",
      "Implemented continuous soil moisture monitoring to activate water pumps only when environmental thresholds are crossed, saving water and improving plant health."
    ]
  },
  {
    id: 'fundamentals',
    title: 'The Fundamentals',
    role: 'Computer Engineering Student',
    year: '2022 – 2023',
    category: ['Fundamentals'],
    tech: [tech.c, tech.cpp, tech.java, tech.python, tech.rust],
    links: {},
    description: [
      "The foundational projects where I learned how systems actually work under the hood. Started with console applications in C and C++, built desktop GUIs in Java, practiced data analysis in Python, and learned memory safety in Rust."
    ],
    collection: [
      { title: 'First Bank System', note: 'A console banking and transaction system.', url: 'https://github.com/Cedrick991/First-Project-Bank-System-' },
      { title: 'ColorGame (Peryahan)', note: 'A C++ version of the classic local peryahan color game.', url: 'https://github.com/Cedrick991/ColorGame-C-' },
      { title: 'PIC Microcontrollers', note: 'Embedded systems projects on PIC microcontrollers.', url: 'https://github.com/Cedrick991/PIC-programming' },
      { title: 'SFML Games', note: 'My first game development projects, in C++ with SFML.', url: 'https://github.com/Cedrick991/smfl_game_try' },
      { title: 'Rust Fundamentals', note: 'Practice projects covering core Rust concepts.', url: 'https://github.com/Cedrick991/rust_fundamentals' }
    ]
  }
]

const activeCategory = ref('All')

const categories = computed(() => [
  'All',
  ...Array.from(new Set(experienceData.flatMap(p => p.category)))
])

const filteredProjects = computed(() =>
  activeCategory.value === 'All'
    ? experienceData
    : experienceData.filter(p => p.category.includes(activeCategory.value))
)

const coreSkills = computed<Tech[]>(() => {
  const seen = new Map<string, Tech>()
  for (const project of experienceData) {
    for (const item of project.tech) {
      if (!seen.has(item.name)) seen.set(item.name, item)
    }
  }
  return Array.from(seen.values())
})
</script>

<template>
  <section class="animate-fade-in w-full flex flex-col">

    <div class="flex flex-col md:flex-row md:items-end justify-between border-b border-gray-300 pb-8 mb-4 gap-8">
      <div class="max-w-xl">
        <span class="text-[10px] uppercase tracking-widest font-bold text-gray-400 mb-3 block">Engineering Log</span>
        <h2 class="text-4xl font-serif text-black">Experience</h2>
      </div>

      <div class="flex flex-wrap gap-2 md:max-w-sm md:justify-end">
        <button
          v-for="cat in categories"
          :key="cat"
          @click="activeCategory = cat"
          :aria-pressed="activeCategory === cat"
          class="px-4 py-2 text-[11px] font-bold uppercase tracking-widest border transition-colors duration-300 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-black"
          :class="activeCategory === cat
            ? 'bg-black text-white border-black'
            : 'bg-transparent text-gray-500 border-gray-200 hover:border-black hover:text-black'"
        >
          {{ cat }}
        </button>
      </div>
    </div>

    <div class="flex flex-col gap-5 border-b border-gray-200 pb-10 mb-4">
      <ul class="flex flex-wrap gap-2" aria-label="Core skills">
        <li
          v-for="skill in coreSkills"
          :key="skill.name"
          class="inline-flex items-center gap-2 border border-gray-200 px-3 py-1.5 text-xs font-bold uppercase tracking-wide text-gray-700 bg-gray-50"
        >
          <img
            v-if="skill.logo"
            :src="skill.logo"
            alt=""
            loading="lazy"
            class="h-4 w-4 object-contain"
          />
          {{ skill.name }}
        </li>
      </ul>
    </div>

    <div class="flex flex-col">
      <article
        v-for="project in filteredProjects"
        :key="project.id"
        class="grid grid-cols-1 md:grid-cols-[5rem_1fr] gap-4 md:gap-10 border-b border-gray-200 py-12 last:border-0"
      >
        <div class="flex items-center gap-2 md:flex-col md:items-end md:gap-1.5 md:border-r md:border-gray-200 md:pr-6 md:pt-1.5">
          <span class="h-1.5 w-1.5 shrink-0 rounded-full bg-black" aria-hidden="true"></span>
          <span class="text-xs font-bold uppercase tracking-widest text-gray-500 whitespace-nowrap">{{ project.year || 'Ongoing' }}</span>
        </div>

        <div class="flex flex-col min-w-0">
          
          <div class="mb-4">
            <h3 class="text-2xl md:text-3xl font-serif text-black leading-tight">{{ project.title }}</h3>
            <span v-if="project.role" class="text-sm font-bold uppercase tracking-widest text-gray-400 mt-2 block">{{ project.role }}</span>
          </div>

          <div v-if="project.description" class="flex flex-col gap-3 mb-6 max-w-3xl">
            <p 
              v-for="(paragraph, index) in project.description" 
              :key="index" 
              class="text-[14px] leading-relaxed text-gray-600"
            >
              {{ paragraph }}
            </p>
          </div>

          <ul v-if="project.collection" class="grid grid-cols-1 md:grid-cols-2 gap-px border border-gray-200 bg-gray-200 mb-6 max-w-3xl">
            <li v-for="item in project.collection" :key="item.title" class="bg-white">
              <a
                :href="item.url"
                target="_blank"
                rel="noopener noreferrer"
                class="flex h-full flex-col gap-1 p-5 transition-colors hover:bg-gray-50 focus-visible:outline focus-visible:outline-2 focus-visible:-outline-offset-2 focus-visible:outline-black"
              >
                <span class="font-serif text-lg text-black">{{ item.title }}</span>
                <span class="text-xs leading-relaxed text-gray-500">{{ item.note }}</span>
              </a>
            </li>
          </ul>

          <ul class="flex flex-wrap gap-2 mb-6" aria-label="Technologies used">
            <li
              v-for="item in project.tech"
              :key="item.name"
              class="inline-flex items-center gap-1.5 px-2 py-1 text-[10px] font-bold uppercase tracking-wider text-gray-500 bg-white border border-gray-200"
            >
              <img v-if="item.logo" :src="item.logo" alt="" loading="lazy" class="h-3 w-3 object-contain opacity-70" />
              {{ item.name }}
            </li>
          </ul>

          <div v-if="project.links.repo || project.links.demo" class="flex gap-6 pt-2">
            <a
              v-if="project.links.repo && project.links.repo !== '#'"
              :href="project.links.repo"
              target="_blank"
              rel="noopener noreferrer"
              class="group flex items-center gap-2 text-[10px] font-bold uppercase tracking-widest text-black hover:text-gray-500 transition-colors"
            >
              View Repository
              <svg class="w-3.5 h-3.5 transform group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
            </a>
            <a
              v-if="project.links.demo"
              :href="project.links.demo"
              target="_blank"
              rel="noopener noreferrer"
              class="group flex items-center gap-2 text-[10px] font-bold uppercase tracking-widest text-black hover:text-gray-500 transition-colors"
            >
              Live Demo
              <svg class="w-3.5 h-3.5 transform group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
            </a>
          </div>

        </div>
      </article>
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