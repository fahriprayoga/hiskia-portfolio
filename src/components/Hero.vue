<template>
  <section class="flex flex-col items-center text-center gap-10 py-10">
    <div class="relative animate-float">
      <div
        class="w-40 h-40 md:w-52 md:h-52 rounded-[3rem] bg-linear-to-tr from-indigo-500 to-purple-600 p-1.5 shadow-2xl shadow-indigo-200">
        <div class="w-full h-full rounded-[2.6rem] bg-white overflow-hidden flex items-center justify-center text-6xl">
          <span class="drop-shadow-xl">👤</span>
        </div>
      </div>
      <div
        class="absolute -bottom-4 -right-4 bg-white p-4 rounded-3xl shadow-xl border border-slate-100 flex items-center gap-2">
        <div class="w-3 h-3 rounded-full bg-green-500 animate-pulse"></div>
        <span class="text-sm font-bold text-slate-700">Open to Work</span>
      </div>
    </div>

    <div class="space-y-6 max-w-3xl">
      <h1 class="text-5xl md:text-7xl font-extrabold text-slate-900 tracking-tight leading-[1.1]">
        Halo, saya <span class="premium-gradient-text">Hiskia Rahadi</span>
      </h1>
      <p class="text-xl md:text-2xl text-slate-600 font-medium max-w-2xl mx-auto">
        Menciptakan <span class="text-indigo-600">pengalaman digital</span> yang mendalam dengan teknologi front-end
        modern dan desain yang berpusat pada manusia.
      </p>

      <div class="flex flex-wrap gap-3 justify-center pt-8">
        <span v-for="tag in tags" :key="tag"
          class="px-5 py-2 glass-card rounded-2xl! text-slate-600 text-sm font-semibold border border-slate-200/50 hover:border-indigo-200 transition-colors cursor-default">
          {{ tag }}
        </span>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { ArrowRight } from "lucide-vue-next";

const tags = ref(["Vue.js Developer", "UI/UX Design", "Performance First", "Clean Architect"]);
</script>
