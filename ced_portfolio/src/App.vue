<script setup lang="ts">
import Sidebar from './components/Sidebar.vue'
import AboutMe from './components/sections/AboutMe.vue'
import Projects from './components/sections/Projects.vue'
import TechStack from './components/sections/TechStack.vue'
import Experience from './components/sections/Experience.vue'
import Certificates from './components/sections/Certificates.vue'
</script>

<template>
  <div class="min-h-screen bg-white text-black">
    <Sidebar />
    <main class="pt-20 md:pt-0 md:ml-60">
      <section id="about" class="px-6 md:px-16 py-16 scroll-mt-20">
        <AboutMe />
      </section>
      <section id="projects" class="px-6 md:px-16 py-16 scroll-mt-20">
        <Projects />
      </section>
      <section id="tech-stack" class="px-6 md:px-16 py-16 scroll-mt-20">
        <TechStack />
      </section>
      <section id="experience" class="px-6 md:px-16 py-16 scroll-mt-20">
        <Experience />
      </section>
      <section id="certificates" class="px-6 md:px-16 py-16 scroll-mt-20">
        <Certificates />
      </section>
    </main>
  </div>
</template>