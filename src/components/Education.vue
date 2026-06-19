<template>
  <section class="space-y-12">
    <div class="flex items-center gap-4">
      <div class="p-3 bg-indigo-600 rounded-2xl shadow-lg shadow-indigo-200">
        <GraduationCap class="text-white w-6 h-6" />
      </div>
      <h2 class="text-3xl font-bold text-slate-800 tracking-tight">Education Background</h2>
    </div>

    <div class="relative pl-10 md:pl-12 border-l-2 border-slate-200 space-y-12">
      <div v-for="(edu, index) in education" :key="index" class="relative">
        <!-- Timeline dot -->
        <div
          class="absolute left-[-3.05rem] md:left-[-3.55rem] top-2 w-6 h-6 rounded-full bg-white border-4 border-indigo-600 shadow-sm">
        </div>

        <div class="glass-card p-6 md:p-8 card-hover border-white/50">
          <div class="flex flex-col md:flex-row md:items-center md:justify-between gap-4 mb-4">
            <div>
              <h3 class="text-xl font-bold text-slate-800">
                {{ edu.degree }}
              </h3>
              <p class="text-indigo-600 font-semibold mt-1">{{ edu.institution }}</p>
            </div>
            <span
              class="text-sm font-bold text-slate-500 bg-slate-100 px-4 py-1.5 rounded-full self-start md:self-auto">
              {{ edu.period }}
            </span>
          </div>
          <p class="text-slate-500 leading-relaxed">{{ edu.description }}</p>
          <div class="mt-6 flex flex-wrap gap-2">
            <span v-for="achievement in edu.achievements" :key="achievement"
              class="text-xs font-bold px-3 py-1 bg-indigo-50 text-indigo-700 rounded-lg border border-indigo-100">
              {{ achievement }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { GraduationCap } from "lucide-vue-next";

const education = ref([
  {
    degree: "S1 Informatika",
    institution: "Universitas Satya Terra Bhinneka",
    period: "2025 - sekarang",
    description: "Specialized in Software Engineering and Human-Computer Interaction. Graduated with honors.",
    achievements: ["IPK 3.8 / 4.0", "Web Dev Society Lead", "UX Research Fellow"],
  },
  {
    degree: "SMK Jurusan Teknik Komputer dan Jaringan",
    institution: "SMK Negeri 1 Cibinong",
    period: "2022 - 2025",
    description: "Immersive training program focused on modern web architectures using Vue.js and Node.js ecosystems.",
    achievements: ["Vue.js Specialist", "Backend Architecture", "Firebase Expert"],
  },
]);
</script>
