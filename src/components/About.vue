<template>
  <section class="glass-card p-10 sm:p-12">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <div class="space-y-6">
        <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-indigo-50 text-indigo-600 text-sm font-semibold">
          <User class="w-4 h-4" />
          <span>About Me</span>
        </div>
        <h2 class="text-4xl font-bold text-slate-800 leading-tight">
          Passionate about creating <br />
          <span class="premium-gradient-text">Exceptional User Experiences</span>
        </h2>
        <p class="text-lg text-slate-600 leading-relaxed">
          I am a dedicated Front-end Developer with a keen eye for detail and a passion for building clean, efficient, and user-centric web applications. My journey in tech is driven by a curiosity to solve complex problems through elegant code and intuitive design.
        </p>
        <p class="text-lg text-slate-600 leading-relaxed">
          With a strong foundation in modern web technologies, I specialize in crafting responsive interfaces that not only look beautiful but also perform flawlessly across all devices.
        </p>
        <div class="flex flex-wrap gap-4 pt-4">
          <div class="flex items-center gap-2 text-slate-700 font-medium">
            <div class="w-2 h-2 rounded-full bg-green-500"></div>
            Available for work
          </div>
          <div class="flex items-center gap-2 text-slate-700 font-medium">
            <div class="w-2 h-2 rounded-full bg-indigo-500"></div>
            Remote specialized
          </div>
        </div>
      </div>
      <div class="relative">
        <div class="aspect-square rounded-[3rem] bg-linear-to-tr from-indigo-100 to-purple-50 overflow-hidden border border-white/50 relative z-10">
          <!-- Image placeholder for user to replace -->
          <div class="w-full h-full flex items-center justify-center text-indigo-300">
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
import { User, Image as ImageIcon } from "lucide-vue-next";
</script>
