<template>
  <div class="min-h-screen bg-slate-50 font-sans antialiased text-slate-900 selection:bg-indigo-100 selection:text-indigo-900">
    <!-- Navbar -->
    <Navbar />

    <!-- Main Content -->
    <main class="max-w-6xl mx-auto px-4 sm:px-6 pt-32 pb-20 sm:pt-40 space-y-24">
      <!-- Hero -->
      <Hero id="hero" />

      <!-- About -->
      <About id="about" />

      <!-- Skills -->
      <Skills id="skills" />

      <!-- Education -->
      <Education id="education" />

      <!-- Contact -->
      <Contact id="contact" />

      <!-- Footer -->
      <Footer />
    </main>
  </div>
</template>

<script setup>
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import About from "./components/About.vue";
import Skills from "./components/Skills.vue";
import Education from "./components/Education.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";
</script>
