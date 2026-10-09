<script setup lang="ts">
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