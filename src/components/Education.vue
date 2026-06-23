<template>
  <section class="space-y-12">
    <div class="flex items-center gap-4">
      <div class="p-3 bg-indigo-600 rounded-2xl shadow-lg shadow-indigo-200">
        <GraduationCap class="text-white w-6 h-6" />
      </div>
      <h2 class="text-3xl font-bold text-slate-800 tracking-tight">Riwayat Pendidikan</h2>
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
    degree: "SDN 173455 Siborboron",
    institution: "Sijamapolang",
    description: "Pendidikan dasar yang menjadi fondasi awal perjalanan belajar.",
    achievements: ["Dasar-dasar Pendidikan"],
  },
  {
    degree: "SMPs Maju Besitang",
    institution: "Langkat",
    description: "Mempelajari dasar-dasar ilmu pengetahuan dan teknologi.",
    achievements: ["Pengenalan Teknologi"],
  },
  {
    degree: "SMKs Maju Besitang - Jurusan TKJ",
    institution: "Langkat",
    description: "Mendalami Teknik Komputer dan Jaringan sebagai bekal karir di bidang IT.",
    achievements: ["Teknik Komputer", "Jaringan", "Dasar Pemrograman"],
  },
]);
</script>