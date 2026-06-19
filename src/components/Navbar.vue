<template>
  <nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-300" :class="[
    isScrolled ? 'py-4 bg-white/70 backdrop-blur-lg shadow-lg border-b border-white/20' : 'py-6 bg-transparent'
  ]">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 flex items-center justify-between">
      <!-- Logo -->
      <div class="flex items-center gap-2 group cursor-pointer" @click="scrollTo('hero')">
        <div
          class="w-10 h-10 bg-indigo-600 rounded-xl flex items-center justify-center shadow-lg shadow-indigo-100 group-hover:scale-110 transition-transform">
          <Sparkles class="text-white w-5 h-5" />
        </div>
        <span class="text-xl font-bold text-slate-800 tracking-tight">
          Hiskia<span class="text-indigo-600">Rahadi</span>
        </span>
      </div>

      <!-- Desktop Links -->
      <div class="hidden md:flex items-center gap-8">
        <a v-for="link in navLinks" :key="link.label" :href="link.href"
          @click.prevent="scrollTo(link.href.substring(1))" class="text-sm font-bold transition-colors" :class="[
            activeSection === link.href.substring(1) ? 'text-indigo-600' : 'text-slate-500 hover:text-indigo-600'
          ]">
          {{ link.label }}
        </a>
        <button @click="scrollTo('contact')"
          class="px-5 py-2.5 bg-indigo-600 text-white rounded-xl text-sm font-bold shadow-lg shadow-indigo-100 hover:bg-indigo-700 transition-all hover:scale-105 active:scale-95">
          Hire Me
        </button>
      </div>

      <!-- Mobile Toggle -->
      <button @click="isMenuOpen = !isMenuOpen"
        class="md:hidden p-2 rounded-xl bg-slate-100 text-slate-600 hover:bg-slate-200 transition-colors">
        <component :is="isMenuOpen ? X : Menu" class="w-6 h-6" />
      </button>
    </div>

    <!-- Mobile Menu -->
    <transition name="mobile-menu">
      <div v-if="isMenuOpen"
        class="md:hidden absolute top-full left-0 right-0 bg-white shadow-2xl border-t border-slate-100 p-6 flex flex-col gap-4 animate-in slide-in-from-top duration-300">
        <a v-for="link in navLinks" :key="link.label" :href="link.href"
          @click.prevent="scrollTo(link.href.substring(1))"
          class="p-4 rounded-2xl text-lg font-bold transition-all border border-transparent" :class="[
            activeSection === link.href.substring(1) ? 'bg-indigo-50 text-indigo-600 border-indigo-100' : 'text-slate-600 hover:bg-slate-50'
          ]">
          {{ link.label }}
        </a>
        <button @click="scrollTo('contact')"
          class="w-full mt-2 py-4 bg-indigo-600 text-white rounded-2xl text-lg font-bold shadow-xl shadow-indigo-100 active:scale-95 transition-all">
          Hire Me
        </button>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import { Sparkles, Menu, X } from "lucide-vue-next";

const navLinks = [
  { label: "Home", href: "#hero" },
  { label: "About", href: "#about" },
  { label: "Skills", href: "#skills" },
  { label: "Education", href: "#education" },
  { label: "Contact", href: "#contact" },
];

const isScrolled = ref(false);
const isMenuOpen = ref(false);
const activeSection = ref("hero");

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20;

  // Update active section
  const sections = navLinks.map(link => link.href.substring(1));
  for (const sectionId of sections.reverse()) {
    const el = document.getElementById(sectionId);
    if (el && window.scrollY >= el.offsetTop - 100) {
      activeSection.value = sectionId;
      break;
    }
  }
};

const scrollTo = (id) => {
  isMenuOpen.value = false;
  const el = document.getElementById(id);
  if (el) {
    window.scrollTo({
      top: el.offsetTop - 80,
      behavior: "smooth",
    });
  }
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
  handleScroll();
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style scoped>
.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: all 0.3s ease;
}

.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
