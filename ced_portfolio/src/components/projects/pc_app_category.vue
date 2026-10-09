<script setup lang="ts">
interface TechItem {
  name: string
  img: string
}

interface TechGroup {
  label: string
  items: TechItem[]
}

interface Project {
  title: string
  description: string
  url: string
  demoUrl?: string
  techStack: TechGroup[]
}

const logoFiles = import.meta.glob('../../../assets/images/*.{webp,png}', {
  eager: true,
  import: 'default'
}) as Record<string, string>

const t = (name: string, file?: string): TechItem => {
  if (!file) return { name, img: '' }
  const foundImage = logoFiles[`../../../assets/images/${file}.webp`] || logoFiles[`../../../assets/images/${file}.png`]
  return { name, img: foundImage ? (foundImage as string) : '' }
}

const projects: Project[] = [
  {
    title: 'Rustotics',
    description: 'An Arduino IDE-like desktop application where you write logic using Rust.',
    url: 'https://github.com/Cedrick991/Rustotics',
    demoUrl: '',
    techStack: [
      { label: 'Languages', items: [t('Rust', 'rust')] },
      { label: 'Frameworks', items: [t('Tauri', 'tauri'), t('React', 'react_logo')] },
      { label: 'IDE', items: [t('VS Code', 'visual_studio')] },
    ]
  },
  {
    title: 'Ced AI',
    description: 'A desktop application exploring practical AI integration, built with Tauri and React.',
    url: 'https://github.com/Cedrick991/ced_Ai',
    demoUrl: '',
    techStack: [
      { label: 'Languages', items: [t('Rust', 'rust')] },
      { label: 'Frameworks', items: [t('Tauri', 'tauri'), t('React', 'react_logo')] },
      { label: 'IDE', items: [t('VS Code', 'visual_studio')] },
    ]
  }
]
</script>

<template>
  <section class="animate-fade-in w-full">
    <div class="grid grid-cols-1 md:grid-cols-2 border-t border-l border-gray-200">

      <div
        v-for="project in projects"
        :key="project.title"
        class="flex flex-col p-6 md:p-8 border-r border-b border-gray-200 bg-white hover:bg-gray-50 transition-colors duration-300"
      >
        <div class="flex flex-col gap-2 mb-6">
          <h3 class="text-xl font-serif text-black">
            {{ project.title }}
          </h3>
          <p class="text-[13px] text-gray-500 leading-relaxed min-h-[40px]">
            {{ project.description }}
          </p>
        </div>

        <div class="flex flex-col gap-2.5 mt-auto">
          <div
            v-for="group in project.techStack"
            :key="group.label"
            class="flex items-start gap-3"
          >
            <span class="text-[8px] font-bold tracking-wide uppercase text-gray-400 w-20 shrink-0 pt-1">
              {{ group.label }}
            </span>

            <div class="flex flex-wrap gap-1.5">
              <div
                v-for="tech in group.items"
                :key="tech.name"
                class="flex items-center gap-1.5 px-2 py-0.5 bg-white border border-gray-200 rounded-sm text-gray-600"
              >
                <img
                  v-if="tech.img"
                  :src="tech.img"
                  :alt="tech.name"
                  class="w-3 h-3 object-contain"
                />
                <span class="text-[8px] font-bold tracking-wider uppercase">
                  {{ tech.name }}
                </span>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-8 flex items-center gap-2">
          <a
            v-if="project.demoUrl"
            :href="project.demoUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="group flex-1 flex items-center justify-between px-4 py-3 bg-black border border-black text-[10px] font-bold uppercase tracking-widest text-white hover:bg-gray-800 transition-colors duration-300 rounded-sm"
          >
            <span>Demo</span>
            <svg class="w-4 h-4 transform group-hover:translate-x-1 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M14 5l7 7m0 0l-7 7m7-7H3"></path>
            </svg>
          </a>
          <a
            :href="project.url"
            target="_blank"
            rel="noopener noreferrer"
            class="group flex items-center px-4 py-3 bg-white border border-gray-200 text-[10px] font-bold uppercase tracking-widest text-gray-600 hover:bg-black hover:text-white hover:border-black transition-all duration-300 rounded-sm"
            :class="project.demoUrl ? '' : 'flex-1 justify-between'"
          >
            <span>{{ project.demoUrl ? 'Code' : 'View Repository' }}</span>
            <svg v-if="!project.demoUrl" class="w-4 h-4 transform group-hover:translate-x-1 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
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