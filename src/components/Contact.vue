<template>
  <section class="glass-card p-8 md:p-12 overflow-hidden relative">
    <div class="absolute top-0 right-0 w-64 h-64 bg-indigo-500/5 rounded-full blur-3xl -mr-32 -mt-32"></div>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
      <div class="space-y-8">
        <div class="space-y-4">
          <h2 class="text-4xl font-bold text-slate-800">
            Mari <span class="premium-gradient-text">Terhubung</span>
          </h2>
          <p class="text-slate-500 max-w-md">
            Sata selalu terbuka untuk mendiskusikan proyek baru, ide kreatif, atau kesempatan untuk menjadi bagian dari
            visi Anda.
          </p>
        </div>

        <div class="space-y-4">
          <div v-for="item in contactInfo" :key="item.label"
            class="flex items-center gap-5 p-4 rounded-2xl hover:bg-slate-50 transition-colors border border-transparent hover:border-slate-100 group">
            <div
              class="w-12 h-12 bg-indigo-50 rounded-xl flex items-center justify-center group-hover:bg-indigo-600 transition-colors duration-300">
              <component :is="item.icon"
                class="w-6 h-6 text-indigo-600 group-hover:text-white transition-colors duration-300" />
            </div>
            <div>
              <p class="text-xs font-bold text-slate-400 uppercase tracking-widest">
                {{ item.label }}
              </p>
              <p class="font-semibold text-slate-700">{{ item.value }}</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Contact Form -->
      <div class="bg-white/50 backdrop-blur-sm rounded-[2.5rem] p-8 md:p-10 border border-white/60 shadow-inner">
        <h3 class="text-2xl font-bold text-slate-800 mb-6">Kirim Pesan</h3>
        <form @submit.prevent="handleSubmit" class="space-y-4">
          <div class="group">
            <input v-model="form.name" type="text" placeholder="Nama Anda"
              class="w-full px-6 py-4 rounded-2xl border border-slate-200 bg-white/80 focus:ring-4 focus:ring-indigo-100 focus:border-indigo-400 outline-none transition-all" />
          </div>
          <div class="group">
            <input v-model="form.email" type="email" placeholder="Email Anda"
              class="w-full px-6 py-4 rounded-2xl border border-slate-200 bg-white/80 focus:ring-4 focus:ring-indigo-100 focus:border-indigo-400 outline-none transition-all" />
          </div>
          <div class="group">
            <textarea v-model="form.message" rows="4" placeholder="Bagaimana saya bisa membantu Anda?"
              class="w-full px-6 py-4 rounded-2xl border border-slate-200 bg-white/80 focus:ring-4 focus:ring-indigo-100 focus:border-indigo-400 outline-none transition-all resize-none"></textarea>
          </div>
          <button type="submit" class="w-full btn-premium btn-primary py-4 text-lg font-bold shadow-indigo-200">
            Kirim Pesan
          </button>
        </form>
        <transition name="fade">
          <p v-if="submitted"
            class="mt-6 p-4 rounded-2xl bg-green-50 text-green-700 text-center font-bold border border-green-100">
            ✓ Pesan berhasil dikirim!
          </p>
        </transition>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from "vue";
import { Mail, Phone, MapPin, Linkedin, Github } from "lucide-vue-next";

const contactInfo = ref([
  { label: "Email", value: "hiskia@email.com", icon: Mail },
  { label: "Lokasi", value: "Medan, Indonesia", icon: MapPin },
  { label: "LinkedIn", value: "linkedin.com/in/hiskia", icon: Linkedin },
  { label: "GitHub", value: "github.com/hiskia", icon: Github },
]);


const form = reactive({
  name: "",
  email: "",
  message: "",
});

const submitted = ref(false);

const handleSubmit = () => {
  console.log("Form submitted:", form);
  submitted.value = true;
  setTimeout(() => {
    submitted.value = false;
    form.name = "";
    form.email = "";
    form.message = "";
  }, 4000);
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
