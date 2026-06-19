<template>
  <section class="space-y-12">
    <div class="text-center space-y-4">
      <h2 class="text-4xl font-bold text-slate-800">
        Skills & <span class="premium-gradient-text">Expertise</span>
      </h2>
      <p class="text-slate-500 max-w-xl mx-auto">
        A diverse set of technical skills and design philosophies that I bring to every project.
      </p>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <div
        v-for="skill in skills"
        :key="skill.name"
        class="glass-card card-hover p-8 group border-white/40"
      >
        <div class="space-y-6">
          <div
            class="w-14 h-14 rounded-2xl bg-indigo-50 flex items-center justify-center group-hover:bg-indigo-600 transition-colors duration-500"
          >
            <component :is="skill.icon" class="w-7 h-7 text-indigo-600 group-hover:text-white transition-colors duration-500" />
          </div>
          <div>
            <h3 class="text-xl font-bold text-slate-800">{{ skill.name }}</h3>
            <p class="text-slate-500 mt-2 leading-relaxed">{{ skill.description }}</p>
            
            <div class="mt-6 flex flex-wrap gap-2">
              <span
                v-for="tag in skill.tags"
                :key="tag"
                class="text-xs font-bold px-3 py-1 bg-slate-100 text-slate-600 rounded-lg group-hover:bg-indigo-50 group-hover:text-indigo-600 transition-colors"
              >
                {{ tag }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import {
  Code2,
  Layout,
  Database,
  Smartphone,
  Palette,
  Zap,
} from "lucide-vue-next";

const skills = ref([
  {
    name: "Frontend Development",
    description: "Building interactive and dynamic user interfaces.",
    icon: Code2,
    tags: ["Vue 3", "React", "TypeScript"],
  },
  {
    name: "UI/UX Design",
    description: "Designing intuitive and aesthetically pleasing interfaces.",
    icon: Layout,
    tags: ["Figma", "Design Systems", "Prototyping"],
  },
  {
    name: "API Integration",
    description: "Seamlessly connecting front-end with robust back-ends.",
    icon: Database,
    tags: ["RESTful", "GraphQL", "Axios"],
  },
  {
    name: "Responsive Design",
    description: "Ensuring optimal performance across all devices.",
    icon: Smartphone,
    tags: ["Mobile-first", "Tailwind CSS", "Flexbox"],
  },
  {
    name: "Creative Engineering",
    description: "Exploring interactive visuals and animations.",
    icon: Palette,
    tags: ["GSAP", "SVG Animation", "Three.js"],
  },
  {
    name: "Performance Mastery",
    description: "Optimizing applications for maximum speed.",
    icon: Zap,
    tags: ["CWV", "Lazy Loading", "Asset Optimization"],
  },
]);
</script>
