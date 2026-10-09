<script setup lang="ts">
import { ref, computed } from 'vue'

import WebCategory from '../projects/web_category.vue'
import EmbeddedCategory from '../projects/embedded_category.vue'
import AndroidAppCategory from '../projects/android_app_category.vue'
import PcAppCategory from '../projects/pc_app_category.vue'
import ExtrasCategory from '../projects/extras_category.vue'

const projectTabs = [
  { id: 'web', label: 'Web', component: WebCategory },
  { id: 'embedded', label: 'Embedded', component: EmbeddedCategory },
  { id: 'android', label: 'Android', component: AndroidAppCategory },
  { id: 'pc', label: 'PC Apps', component: PcAppCategory },
  { id: 'extras', label: 'Extras', component: ExtrasCategory }
]

const activeProjectTabId = ref('web')

const activeComponent = computed(() => {
  return projectTabs.find(tab => tab.id === activeProjectTabId.value)?.component
})
</script>

<template>
  <div class="animate-fade-in flex flex-col w-full">
    
    <div class="flex flex-col md:flex-row md:items-end justify-between border-b border-gray-300 pb-6 mb-8 gap-6">
      <div>
        <span class="text-[9px] uppercase tracking-widest font-bold text-gray-400 mb-3 block">Selected Work</span>
        <h2 class="text-4xl font-serif text-black">Projects</h2>
      </div>

      <div class="flex flex-wrap gap-2">
        <button
          v-for="tab in projectTabs"
          :key="tab.id"
          @click="activeProjectTabId = tab.id"
          class="px-5 py-2 text-[10px] font-bold uppercase tracking-widest border transition-all duration-300"
          :class="activeProjectTabId === tab.id ? 'bg-black text-white border-black' : 'bg-transparent text-gray-400 border-gray-200 hover:border-black hover:text-black'"
        >
          {{ tab.label }}
        </button>
      </div>
    </div>

    <div class="w-full">
      <component :is="activeComponent" />
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
</style>