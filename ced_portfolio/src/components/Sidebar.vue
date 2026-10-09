<script setup lang="ts">
import myCV from '../assets/cv/CEDRICK_UNIDA_RESUME.docx?url'

const sections = [
  { id: 'about', label: 'About me' },
  { id: 'projects', label: 'Projects' },
  { id: 'tech-stack', label: 'Tech stack' },
  { id: 'experience', label: 'Experience' },
  { id: 'certificates', label: 'Certificates' }
]
</script>

<template>
  <aside
    class="flex flex-col md:flex-col md:items-start md:justify-start
           border-b md:border-b-0 md:border-r border-gray-200 bg-white
           px-6 py-5 md:px-8 md:py-10
           md:fixed md:left-0 md:top-0 md:h-screen md:w-60 z-10 w-full"
  >
    <div class="mb-4 md:mb-0">
      <h1 class="text-xl md:text-2xl font-serif text-black">John Cedrick F. Unida</h1>
      <p class="hidden md:block text-xs text-gray-500 mt-1">Computer Engineering Student</p>
    </div>

    <nav class="w-full md:mt-12">
      <ul class="flex gap-5 overflow-x-auto w-full pb-2 md:pb-0 md:flex-col md:gap-4 md:overflow-visible no-scrollbar">
        <li v-for="section in sections" :key="section.id" class="shrink-0">
          <a
            :href="`#${section.id}`"
            class="text-[11px] font-bold tracking-widest uppercase text-gray-500 hover:text-black
                   transition-colors duration-300 whitespace-nowrap"
          >
            {{ section.label }}
          </a>
        </li>
      </ul>
    </nav>

    <div class="mt-4 md:mt-auto w-full flex items-center gap-5 overflow-x-auto no-scrollbar md:flex-col md:items-start md:gap-4 md:border-t md:border-gray-200 md:pt-8 md:pb-2">
      
      <a :href="myCV" download class="group flex items-center gap-2 text-[10px] font-bold tracking-widest uppercase text-black hover:text-gray-500 transition-colors duration-300 shrink-0">
        <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"></path></svg>
        <span>Resume</span>
      </a>

      <a href="mailto:unidacedrick80@gmail.com" class="group flex items-center gap-2 text-[10px] font-bold tracking-widest uppercase text-gray-400 hover:text-black transition-colors duration-300 shrink-0">
        <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>
        <span>Email</span>
      </a>

      <a href="https://github.com/Cedrick991" target="_blank" rel="noopener noreferrer" class="group flex items-center gap-2 text-[10px] font-bold tracking-widest uppercase text-gray-400 hover:text-black transition-colors duration-300 shrink-0">
        <svg class="w-3.5 h-3.5" fill="currentColor" viewBox="0 0 24 24"><path fill-rule="evenodd" d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z" clip-rule="evenodd" /></svg>
        <span>GitHub</span>
      </a>

      <a href="https://www.linkedin.com/in/john-cedrick-unida-72b6a6397/?isSelfProfile=true" target="_blank" rel="noopener noreferrer" class="group flex items-center gap-2 text-[10px] font-bold tracking-widest uppercase text-gray-400 hover:text-black transition-colors duration-300 shrink-0">
        <svg class="w-3.5 h-3.5" fill="currentColor" viewBox="0 0 24 24"><path fill-rule="evenodd" d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z" clip-rule="evenodd" /></svg>
        <span>LinkedIn</span>
      </a>
      
    </div>
  </aside>
</template>

<style scoped>
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>