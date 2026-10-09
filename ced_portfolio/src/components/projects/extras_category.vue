<script setup lang="ts">
interface Proof {
  title: string
  url: string
}

interface LanguageGroup {
  name: string
  img: string
  proofs: Proof[]
}

const logoFiles = import.meta.glob('../../assets/images/*.{webp,png}', {
  eager: true,
  import: 'default'
}) as Record<string, string>

const getIcon = (file: string): string => {
  const found = logoFiles[`../../assets/images/${file}.webp`] || logoFiles[`../../assets/images/${file}.png`]
  return found ? (found as string) : ''
}

const languages: LanguageGroup[] = [
  {
    name: 'JavaScript',
    img: getIcon('javascript'),
    proofs: [
      { title: 'Will U Be My Valentine', url: 'https://github.com/Cedrick991/willubemyvalentine' },
      { title: 'My Pretty Little Baby', url: 'https://github.com/Cedrick991/My-Pretty-LittleBaby' },
    ]
  },
  {
    name: 'TypeScript',
    img: getIcon('typescript'),
    proofs: [
      { title: 'Retailer Manager', url: 'https://github.com/Cedrick991/RetailerManager' },
      { title: 'CedLMS', url: 'https://github.com/Cedrick991/CedLMS-Learning-Management-System-NodeJs' },
      { title: 'AtinaGift', url: 'https://github.com/Cedrick991/AtinaGift_Proj'},
    ]
  },
  {
    name: 'Rust',
    img: getIcon('rust'),
    proofs: [
      { title: 'Rust Fundamentals', url: 'https://github.com/Cedrick991/rust_fundamentals' },
    ]
  },
  {
    name: 'C++',
    img: getIcon('cpp_logo'),
    proofs: [
      { title: 'First Bank System', url: 'https://github.com/Cedrick991/First-Project-Bank-System-' },
      { title: 'ColorGame (Peryahan)', url: 'https://github.com/Cedrick991/ColorGame-C-' },
      { title: 'C and C++ Fundamentals', url: 'https://github.com/Cedrick991/c-and-cpp-practice-fundamentals' },
      { title: 'SFML Games', url: 'https://github.com/Cedrick991/smfl_game_try' },
      { title: 'PIC Microcontrollers', url: 'https://github.com/Cedrick991/PIC-programming' },
    ]
  },
  {
    name: 'C',
    img: getIcon('c'),
    proofs: [
      { title: 'C and C++ Fundamentals', url: 'https://github.com/Cedrick991/c-and-cpp-practice-fundamentals' },
      { title: 'PIC Microcontrollers', url: 'https://github.com/Cedrick991/PIC-programming' },
    ]
  },
  {
    name: 'Java',
    img: getIcon('java'),
    proofs: [
      { title: 'Java and JavaFX', url: 'https://github.com/Cedrick991/java-fundamentals' },
      { title: 'Drone View App', url: 'https://github.com/Cedrick991/drone_viewApp' },
    ]
  },
  {
    name: 'Kotlin',
    img: getIcon('kotlin'),
    proofs: [
      { title: 'Drone View App', url: 'https://github.com/Cedrick991/drone_viewApp' },
    ]
  },
  {
    name: 'PHP',
    img: getIcon('php'),
    proofs: [
      { title: 'Vet Clinic', url: 'https://github.com/Cedrick991/vetclinic' },
    ]
  },
  {
    name: 'Python',
    img: getIcon('python'),
    proofs: [
      { title: 'Python and Data Analysis', url: 'https://github.com/Cedrick991/Python-Data-Analyst-essentials-and-Python-Fundamentals' },
    ]
  },
  {
    name: 'Assembly',
    img: getIcon('assembly'),
    proofs: [
      { title: 'PIC Microcontrollers', url: 'https://github.com/Cedrick991/PIC-programming' },
    ]
  },
]
</script>

<template>
  <section class="animate-fade-in w-full">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 border-t border-l border-gray-200">

      <div
        v-for="lang in languages"
        :key="lang.name"
        class="flex flex-col p-6 md:p-8 border-r border-b border-gray-200 bg-white hover:bg-gray-50 transition-colors duration-300"
      >
        <div class="flex items-center gap-3 mb-5">
          <img
            v-if="lang.img"
            :src="lang.img"
            :alt="lang.name"
            class="w-7 h-7 object-contain"
          />
          <span v-else class="font-serif text-2xl text-gray-300">
            {{ lang.name.charAt(0) }}
          </span>
          <h3 class="text-xl font-serif text-black">
            {{ lang.name }}
          </h3>
        </div>

        <div class="flex flex-col">
          <a
            v-for="proof in lang.proofs"
            :key="proof.title"
            :href="proof.url"
            target="_blank"
            rel="noopener noreferrer"
            class="group flex items-center justify-between gap-3 py-2.5 border-t border-gray-100 first:border-t-0 text-gray-500 hover:text-black transition-colors duration-200"
          >
            <span class="text-[13px]">
              {{ proof.title }}
            </span>
            <svg class="w-3.5 h-3.5 text-gray-300 group-hover:text-black transform group-hover:translate-x-0.5 transition-all duration-200 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M14 5l7 7m0 0l-7 7m7-7H3"></path>
            </svg>
          </a>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.animate-fade-in {
  animation: fadeIn 0.3s ease-out;
}
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(5px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>