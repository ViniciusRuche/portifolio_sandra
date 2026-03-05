<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isMobileMenuOpen = ref(false);
const activeDropdown = ref(null);
const navLinks = [
  { text: 'Sobre Mim', url: '#sobre' },
  { text: 'Espaço', url: '#espaco' },
  { text: 'Especialidades', url: '#especialidades' },
  { text: 'Formação', 
    url: '',
    dropdown: [
      { text: 'Qualificação & Atuação Profissional', url: '#qualificacao' },
      { text: 'Diplomas & Certificações', url: '#certificados' },
    ]
   },
];

const toggleMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
  activeDropdown.value = null; 
};

const toggleDropdown = (label) => {
  activeDropdown.value = activeDropdown.value === label ? null : label;
};

const closeDropdowns = (e) => {
  if (!e.target.closest('.dropdown-container')) {
    activeDropdown.value = null;
  }
};

onMounted(() => window.addEventListener('click', closeDropdowns));
onUnmounted(() => window.removeEventListener('click', closeDropdowns));
</script>

<template>
  <nav class="fixed top-0 left-0 w-full h-[70px] bg-white shadow-sm flex items-center justify-center z-[1000] px-5">
    <div class="w-full max-w-[1200px] flex items-center justify-between">
      
      <a href="#" class="flex items-center gap-2 text-emerald-600 font-bold text-xl tracking-tighter">
        <div class="p-1 rounded-lg">
          <img class="w-6 h-6" src="/favicon/icon-sandra.png" alt="Sandra Oliveira">
        </div>
        SANDRA<span class="text-slate-400 font-light">OLIVEIRA</span>
      </a>

      <ul :class="[
        'flex gap-8 items-center transition-all duration-300',
        isMobileMenuOpen 
          ? 'absolute top-[70px] left-0 w-full bg-white border-b border-slate-100 p-8 flex-col shadow-xl' 
          : 'hidden md:flex'
      ]">
        <li v-for="link in navLinks" :key="link.text" class="relative dropdown-container w-full md:w-auto text-center">
          
          <a v-if="!link.dropdown" 
             :href="link.url" 
             @click="isMobileMenuOpen = false"
             class="text-[0.8rem] font-bold tracking-widest text-slate-500 hover:text-emerald-600 transition-colors">
            {{ link.text }}
          </a>

          <template v-else>
            <button @click="toggleDropdown(link.text)" 
                    class="flex items-center justify-center gap-1 w-full text-[0.8rem] font-bold tracking-widest text-slate-500 hover:text-emerald-600 transition-colors">
              {{ link.text }}
              <svg :class="['w-3 h-3 transition-transform', activeDropdown === link.text ? 'rotate-180' : '']" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="m6 9 6 6 6-6"/></svg>
            </button>

            <ul v-show="activeDropdown === link.text" 
                class="md:absolute top-full left-0 mt-2 min-w-[200px] bg-white md:shadow-2xl md:border border-slate-100 rounded-xl p-2 space-y-1">
              <li v-for="sub in link.dropdown" :key="sub.text">
                <a :href="sub.url" 
                   @click="isMobileMenuOpen = false; activeDropdown = null"
                   class="block px-4 py-2 text-[0.75rem] text-slate-500 hover:bg-emerald-50 hover:text-emerald-600 rounded-lg font-medium transition-all">
                  {{ sub.text }}
                </a>
              </li>
            </ul>
          </template>
        </li>
      </ul>

      <div class="flex items-center gap-4">
        <a href="#contato" class="bg-emerald-600 text-white px-6 py-2.5 rounded-full text-[0.75rem] font-bold tracking-widest hover:bg-emerald-700 shadow-lg shadow-emerald-200 transition-all">
          CONTATO
        </a>

        <div class="md:hidden flex flex-col gap-1 cursor-pointer" @click="toggleMenu">
          <span :class="['w-6 h-[2px] bg-slate-800 transition-all', isMobileMenuOpen ? 'rotate-45 translate-y-1.5' : '']"></span>
          <span :class="['w-6 h-[2px] bg-slate-800 transition-all', isMobileMenuOpen ? 'opacity-0' : '']"></span>
          <span :class="['w-6 h-[2px] bg-slate-800 transition-all', isMobileMenuOpen ? '-rotate-45 -translate-y-1.5' : '']"></span>
        </div>
      </div>
    </div>
  </nav>
</template>