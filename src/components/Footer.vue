<template>
  <footer class="glass-card p-10 md:p-12 mt-20 border-white/40">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-12">
      <!-- Brand & Description -->
      <div class="space-y-6">
        <div class="flex items-center gap-3">
          <div class="w-10 h-10 bg-indigo-600 rounded-xl flex items-center justify-center shadow-lg shadow-indigo-100">
            <Sparkles class="text-white w-5 h-5" />
          </div>
          <span class="text-2xl font-bold text-slate-800 tracking-tight">
            Andre<span class="text-indigo-600">Pratama</span>
          </span>
        </div>
        <p class="text-slate-500 leading-relaxed max-w-xs">
          Membangun pengalaman digital yang bermakna melalui estetika modern dan kode yang terarah.
        </p>
        <div class="flex gap-4">
          <a v-for="social in socialLinks" :key="social.label" :href="social.url" target="_blank"
            class="w-10 h-10 bg-white border border-slate-100 rounded-xl flex items-center justify-center hover:bg-slate-50 hover:border-indigo-200 transition-all hover:-translate-y-1 group">
            <component :is="social.icon" class="w-5 h-5 text-slate-400 group-hover:text-indigo-600 transition-colors" />
          </a>
        </div>
      </div>

      <!-- Quick Links -->
      <div class="space-y-6">
        <h4 class="text-lg font-bold text-slate-800">Navigasi</h4>
        <ul class="space-y-3">
          <li v-for="link in navLinks" :key="link.label">
            <a :href="link.href"
              class="group flex items-center gap-3 text-slate-500 hover:text-indigo-600 transition-colors font-medium">
              <div class="w-1.5 h-1.5 rounded-full bg-slate-200 group-hover:bg-indigo-400 transition-colors"></div>
              {{ link.label }}
            </a>
          </li>
        </ul>
      </div>

      <!-- Newsletter -->
      <div class="space-y-6">
        <h4 class="text-lg font-bold text-slate-800">Tetap Terhubung</h4>
        <p class="text-slate-500 text-sm">
          Ikuti newsletter saya untuk mendapatkan update terbaru tentang proyek dan tulisan saya.
        </p>
        <form @submit.prevent="handleSubscribe" class="flex flex-col sm:flex-row gap-3">
          <input v-model="emailSubs" type="email" placeholder="nama@email.com" required
            class="flex-1 px-5 py-3 rounded-xl border border-slate-200 bg-white/50 focus:ring-4 focus:ring-indigo-100 focus:border-indigo-400 outline-none transition-all text-sm" />
          <button type="submit"
            class="px-6 py-3 bg-indigo-600 text-white rounded-xl hover:bg-indigo-700 transition-all shadow-lg shadow-indigo-100 flex items-center justify-center gap-2">
            <Send class="w-4 h-4" />
          </button>
        </form>
        <transition name="fade">
          <p v-if="subscribed" class="text-sm font-bold text-green-600">
            ✓ Berhasil berlangganan!
          </p>
        </transition>
      </div>
    </div>

    <!-- Bottom Bar -->
    <div
      class="mt-16 pt-8 border-t border-slate-100 flex flex-col md:flex-row justify-between items-center gap-6 text-sm text-slate-400">
      <p>
        &copy; {{ currentYear }}
        <span class="text-slate-700 font-bold">Hiskia Rahadi</span>. Dibuat dengan
        <Heart class="w-4 h-4 inline text-rose-500 fill-rose-500/20" />
        kualitas tinggi.
      </p>
      <div class="flex items-center gap-6">
        <a href="#" class="hover:text-indigo-600 transition-colors">Kebijakan Privasi</a>
        <a href="#" class="hover:text-indigo-600 transition-colors">Syarat Ketentuan</a>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref, computed } from "vue";
import {
  Github,
  Linkedin,
  Instagram,
  Twitter,
  Sparkles,
  Send,
  Heart,
  Globe,
} from "lucide-vue-next";

const currentYear = computed(() => new Date().getFullYear());

const socialLinks = ref([
  { label: "GitHub", icon: Github, url: "#" },
  { label: "LinkedIn", icon: Linkedin, url: "#" },
  { label: "Instagram", icon: Instagram, url: "#" },
  { label: "Twitter", icon: Twitter, url: "#" },
]);

const navLinks = ref([
  { label: "Beranda", href: "#hero" },
  { label: "Tentang", href: "#about" },
  { label: "Keahlian", href: "#skills" },
  { label: "Pendidikan", href: "#education" },
  { label: "Kontak", href: "#contact" },
]);

const emailSubs = ref("");
const subscribed = ref(false);

const handleSubscribe = () => {
  if (emailSubs.value) {
    subscribed.value = true;
    setTimeout(() => {
      subscribed.value = false;
      emailSubs.value = "";
    }, 4000);
  }
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
