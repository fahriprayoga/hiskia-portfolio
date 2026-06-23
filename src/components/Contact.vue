<template>
  <section class="glass-card p-8 md:p-12 overflow-hidden relative">
    <div class="absolute top-0 right-0 w-64 h-64 bg-indigo-500/5 rounded-full blur-3xl -mr-32 -mt-32"></div>

    <div class="space-y-8">
      <div class="space-y-4 text-center">
        <h2 class="text-4xl font-bold text-slate-800">
          Mari <span class="premium-gradient-text">Terhubung</span>
        </h2>
        <p class="text-slate-500 max-w-md mx-auto">
          Saya selalu terbuka untuk mendiskusikan proyek baru, ide kreatif, atau kesempatan untuk menjadi bagian dari
          visi Anda. Jangan ragu untuk menghubungi saya melalui kontak di bawah ini.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 max-w-4xl mx-auto">
        <div v-for="item in contactInfo" :key="item.label"
          class="flex flex-col items-center gap-4 p-6 rounded-2xl bg-white/50 backdrop-blur-sm border border-white/60 hover:border-indigo-200 transition-all hover:-translate-y-1 group">
          <div
            class="w-16 h-16 bg-indigo-50 rounded-2xl flex items-center justify-center group-hover:bg-indigo-600 transition-colors duration-300">
            <component :is="item.icon"
              class="w-8 h-8 text-indigo-600 group-hover:text-white transition-colors duration-300" />
          </div>
          <div class="text-center">
            <p class="text-xs font-bold text-slate-400 uppercase tracking-widest mb-1">
              {{ item.label }}
            </p>
            <p v-if="item.value" class="font-semibold text-slate-700">{{ item.value }}</p>
            <a v-else-if="item.href" :href="item.href" target="_blank"
              class="font-semibold text-indigo-600 hover:text-indigo-800 transition-colors">
              {{ item.display }}
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { Instagram, Phone, Mail } from "lucide-vue-next";

const contactInfo = ref([
  {
    label: "Instagram",
    icon: Instagram,
    href: "https://instagram.com/adi_hiskia",
    display: "@adi_hiskia"
  },
  {
    label: "WhatsApp",
    icon: Phone,
    value: "0831 3238 0999"
  },
  {
    label: "Gmail",
    icon: Mail,
    value: "hiskialg@gmail.com"
  },
]);
</script>