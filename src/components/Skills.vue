<template>
  <section class="space-y-12">
    <div class="text-center space-y-4">
      <h2 class="text-4xl font-bold text-slate-800">
        Keterampilan & <span class="premium-gradient-text">Minat yang Ingin Dikembangkan</span>
      </h2>
      <p class="text-slate-500 max-w-xl mx-auto">
        Beberapa bidang yang sedang saya pelajari dan dalami, serta area pengembangan diri ke depan.
      </p>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <div v-for="skill in skills" :key="skill.name" class="glass-card card-hover p-8 group border-white/40">
        <div class="space-y-6">
          <div
            class="w-14 h-14 rounded-2xl bg-indigo-50 flex items-center justify-center group-hover:bg-indigo-600 transition-colors duration-500">
            <component :is="skill.icon"
              class="w-7 h-7 text-indigo-600 group-hover:text-white transition-colors duration-500" />
          </div>
          <div>
            <h3 class="text-xl font-bold text-slate-800">{{ skill.name }}</h3>
            <p class="text-slate-500 mt-2 leading-relaxed">{{ skill.description }}</p>

            <div class="mt-6 flex flex-wrap gap-2">
              <span v-for="tag in skill.tags" :key="tag"
                class="text-xs font-bold px-3 py-1 bg-slate-100 text-slate-600 rounded-lg group-hover:bg-indigo-50 group-hover:text-indigo-600 transition-colors">
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
  Server,
  Wifi,
  Cpu,
  Zap,
} from "lucide-vue-next";

const skills = ref([
  {
    name: "Jaringan Komputer",
    description: "Memahami dasar-dasar jaringan, topologi, dan konfigurasi perangkat jaringan.",
    icon: Wifi,
    tags: ["TCP/IP", "Routing", "Switching", "LAN/WAN"],
  },
  {
    name: "Hardware Komputer",
    description: "Mendalami komponen perangkat keras, instalasi, dan troubleshooting.",
    icon: Cpu,
    tags: ["CPU", "RAM", "Motherboard", "Periferal"],
  },
  {
    name: "Pengembangan Web (Belajar)",
    description: "Sedang dalam proses belajar pengembangan web front-end modern.",
    icon: Code2,
    tags: ["Vue 3", "HTML/CSS", "JavaScript", "Tailwind"],
  },
  {
    name: "UI/UX Design (Belajar)",
    description: "Mempelajari prinsip desain antarmuka untuk pengalaman pengguna yang baik.",
    icon: Layout,
    tags: ["Figma", "Prototyping", "Sistem Desain"],
  },
  {
    name: "Infrastruktur IT",
    description: "Memahami dasar-dasar infrastruktur teknologi informasi dan server.",
    icon: Server,
    tags: ["Server", "Cloud Computing", "Virtualisasi"],
  },
  {
    name: "Optimasi Sistem",
    description: "Mempelajari cara mengoptimalkan kinerja sistem dan perangkat.",
    icon: Zap,
    tags: ["Performance", "Monitoring", "Troubleshooting"],
  },
]);
</script>