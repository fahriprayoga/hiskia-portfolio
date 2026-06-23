<template>
  <section class="glass-card p-10 sm:p-12">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <div class="space-y-6">
        <div
          class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-indigo-50 text-indigo-600 text-sm font-semibold">
          <User class="w-4 h-4" />
          <span>Tentang Saya</span>
        </div>
        <h2 class="text-4xl font-bold text-slate-800 leading-tight">
          Berdedikasi untuk <span class="premium-gradient-text">Memahami dan Mendalami</span><br />
          Dunia Teknologi
        </h2>
        <p class="text-lg text-slate-600 leading-relaxed">
          Saya memiliki ketertarikan yang mendalam pada dunia <span class="font-semibold text-slate-800">jaringan
            komputer</span>
          dan <span class="font-semibold text-slate-800">hardware</span>. Saya senang mempelajari bagaimana sistem
          bekerja, mulai dari perangkat keras hingga konektivitas jaringan yang menghubungkan semuanya.
        </p>
        <p class="text-lg text-slate-600 leading-relaxed">
          Saat ini, saya juga sedang dalam tahap <span class="font-semibold text-indigo-600">mengembangkan diri</span>
          di bidang <span class="font-semibold text-slate-800">pengembangan web</span>. Meskipun masih dalam proses
          belajar, saya terus berusaha untuk memahami teknologi front-end modern dan menerapkannya dalam proyek-proyek
          kecil sebagai bentuk latihan dan pengembangan kemampuan.
        </p>
        <div class="flex flex-wrap gap-4 pt-4">
          <div class="flex items-center gap-2 text-slate-700 font-medium">
            <div class="w-2 h-2 rounded-full bg-green-500"></div>
            Tersedia untuk bekerja
          </div>
          <div class="flex items-center gap-2 text-slate-700 font-medium">
            <div class="w-2 h-2 rounded-full bg-indigo-500"></div>
            Terus Belajar & Berkembang
          </div>
        </div>
      </div>
      <div class="relative">
        <div
          class="aspect-square rounded-[3rem] bg-linear-to-tr from-indigo-100 to-purple-50 overflow-hidden border border-white/50 relative z-10">
          <!-- Profile Image -->
          <img v-if="profileImage" :src="profileImage" :alt="profileName" class="w-full h-full object-cover" />
          <!-- Placeholder if no image -->
          <div v-else class="w-full h-full flex items-center justify-center text-indigo-300">
            <ImageIcon class="w-24 h-24 stroke-[1px]" />
          </div>
        </div>
        <!-- Decorative elements -->
        <div class="absolute -top-6 -right-6 w-32 h-32 bg-indigo-200/30 rounded-full blur-3xl animate-pulse"></div>
        <div class="absolute -bottom-10 -left-10 w-48 h-48 bg-purple-200/20 rounded-full blur-3xl"></div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { User, Image as ImageIcon } from "lucide-vue-next";
import profileImage from "./../assets/image.png";

const profileName = ref("Hiskia Rahadi");
</script>
