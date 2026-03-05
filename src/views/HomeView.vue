<script setup>
import NavBar from '@/views/components/NavBar.vue'
import Header from '@/views/components/Header.vue'
import SobreMim from '@/views/components/SobreMim.vue'
import Espaco from '@/views/components/Espaco.vue'
import Especialidades from '@/views/components/Especialidades.vue'
import Certificados from '@/views/components/Certificados.vue'
import Contatos from '@/views/components/Contatos.vue'
import Separator from '@/components/ui/separator/Separator.vue'
import Profissional from './components/Profissional.vue'
import { Facebook, Instagram, MessageCircle } from 'lucide-vue-next'
</script>

<template>
  <div class="min-h-screen bg-[#050505]"> 
    <NavBar />
    <Header />
    <SobreMim />
    <Espaco />
    <Especialidades />
    <Profissional />
    <Certificados /> 
    <Contatos />
    <Separator class="bg-indigo-500/30 w-[80%] mx-auto"/> 
    <footer class="bg-white py-16 border-t border-slate-100">
    <div class="container mx-auto px-6">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-16 lg:gap-32 text-center md:text-left pb-12">
        
        <div class="space-y-4">
          <h3 class="text-emerald-600 font-bold text-xl tracking-tighter uppercase">
            SANDRA<span class="text-slate-400 font-light">OLIVEIRA</span>
          </h3>
          <p class="text-slate-500 text-sm leading-relaxed max-w-xs mx-auto md:mx-0 font-medium italic">
            "Equipamentos modernos e técnicas neurofisiológicas para resultados rápidos e duradouros."
          </p>
        </div>

        <div class="space-y-4">
          <h4 class="text-slate-800 font-bold text-xs uppercase tracking-widest">Onde Estamos</h4>
          <p class="text-slate-500 text-sm leading-relaxed">
            Centro Comercial Metropolitan<br/>
            Rua Pinheiro Machado, Nº 2705, sala 703<br/>
            Caxias do Sul, RS
          </p>
        </div>

        <div class="space-y-4">
          <h4 class="text-slate-800 font-bold text-xs uppercase tracking-widest">Siga-nos</h4>
          <div class="flex justify-center md:justify-start gap-6">
            <a href="#" class="w-10 h-10 rounded-full bg-emerald-50 flex items-center justify-center text-emerald-600 hover:bg-emerald-600 hover:text-white transition-all">
              <Instagram size="20" />
            </a>
            <a href="#" class="w-10 h-10 rounded-full bg-emerald-50 flex items-center justify-center text-emerald-600 hover:bg-emerald-600 hover:text-white transition-all">
              <Facebook size="20" />
            </a>
            <a href="#" class="w-10 h-10 rounded-full bg-emerald-50 flex items-center justify-center text-emerald-600 hover:bg-emerald-600 hover:text-white transition-all">
              <MessageCircle size="20" />
            </a>
          </div>
        </div>
      </div>

      <div class="pt-10 flex flex-col md:flex-row justify-between items-center gap-4 border-t border-slate-50">
        <p class="text-[10px] text-slate-400 font-bold uppercase tracking-widest">
          © 2026 - SANDRA OLIVEIRA. TODOS OS DIREITOS RESERVADOS.
        </p>
        <p class="text-[10px] text-slate-400 font-medium uppercase tracking-tight">
          Desenvolvido por <span class="text-emerald-500 font-bold">Vinícius Ruche</span>
        </p>
      </div>
    </div>
  </footer>
  </div>
</template>