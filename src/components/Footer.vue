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
            Hiskia<span class="text-indigo-600">Rahadi</span>
          </span>
        </div>
        <p class="text-slate-500 leading-relaxed max-w-xs">
          Mendalami dan memahami pengalaman digital melalui estetika modern dan kode yang terarah.
        </p>
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

      <!-- Social & Contact -->
      <div class="space-y-6">
        <h4 class="text-lg font-bold text-slate-800">Hubungi Saya</h4>
        <div class="space-y-3">
          <div v-for="contact in contacts" :key="contact.label" class="flex items-center gap-3 text-slate-500">
            <component :is="contact.icon" class="w-5 h-5 text-indigo-600" />
            <span>{{ contact.value }}</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Bottom Bar -->
    <div
      class="mt-16 pt-8 border-t border-slate-100 flex flex-col md:flex-row justify-between items-center gap-6 text-sm text-slate-400">
      <p>
        &copy; {{ currentYear }}
        <span class="text-slate-700 font-bold">Hiskia Rahadi</span>. Dibuat dengan
        <Heart class="w-4 h-4 inline text-rose-500 fill-rose-500/20" />
        dedikasi tinggi.
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
  Heart,
  Mail,
  Phone,
} from "lucide-vue-next";

const currentYear = computed(() => new Date().getFullYear());

const socialLinks = ref([
  { label: "GitHub", icon: Github, url: "#" },
  { label: "LinkedIn", icon: Linkedin, url: "#" },
  { label: "Instagram", icon: Instagram, url: "https://instagram.com/adi_hiskia" },
  { label: "Twitter", icon: Twitter, url: "#" },
]);

const contacts = ref([
  { label: "Instagram", icon: Instagram, value: "@adi_hiskia" },
  { label: "WhatsApp", icon: Phone, value: "0831 3238 0999" },
  { label: "Gmail", icon: Mail, value: "hiskialg@gmail.com" },
]);

const navLinks = ref([
  { label: "Beranda", href: "#hero" },
  { label: "Tentang", href: "#about" },
  { label: "Keterampilan", href: "#skills" },
  { label: "Pendidikan", href: "#education" },
  { label: "Kontak", href: "#contact" },
]);
</script>