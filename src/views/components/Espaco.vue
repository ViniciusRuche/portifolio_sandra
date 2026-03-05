<script setup>
import { Building2, MapPin, ShieldCheck, Thermometer, UserCheck } from 'lucide-vue-next'

const images = [
  { url: 'https://images.unsplash.com/photo-1589829545856-d10d557cf95f?w=800&q=80', alt: 'Interior moderno do consultório no Tronca Corporate' },
  { url: 'https://images.unsplash.com/photo-1589829545856-d10d557cf95f?w=800&q=80', alt: 'Equipamento de laser profissional para auriculoterapia' },
  { url: 'https://images.unsplash.com/photo-1589829545856-d10d557cf95f?w=800&q=80', alt: 'Ambiente de atendimento climatizado e privativo' },
  { url: 'https://images.unsplash.com/photo-1589829545856-d10d557cf95f?w=800&q=80', alt: 'Detalhe de equipamentos modernos de massoterapia' }
]
</script>

<template>
  <section id="espaco" class="py-24 bg-[#fdfaf5]">
    <div class="container mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        
        <div class="space-y-8 order-2 lg:order-1">
          <div class="space-y-4">
            <h4 class="text-emerald-600 font-bold tracking-[0.3em] text-xs uppercase">Onde Cuidamos de Você</h4>
            <h2 class="text-3xl md:text-4xl font-serif text-slate-800 leading-tight">
              Nosso <span class="italic text-emerald-600">espaço</span>
            </h2>
            <p class="text-slate-600 text-lg leading-relaxed">
              Estamos localizados num dos melhores espaços da cidade de Caxias do Sul: 
              <span class="font-bold text-slate-800">Centro Comercial Metropolitan</span>.
            </p>
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
            <div class="flex gap-4 items-start">
              <div class="p-2 bg-emerald-100 rounded-lg text-emerald-700">
                <MapPin size="20" />
              </div>
              <div>
                <h5 class="text-sm font-bold text-slate-800 uppercase tracking-wide">Localização</h5>
                <p class="text-xs text-slate-500 mt-1">Rua Pinheiro Machado, Nº 2705, sala 703.</p>
              </div>
            </div>

            <div class="flex gap-4 items-start">
              <div class="p-2 bg-emerald-100 rounded-lg text-emerald-700">
                <Building2 size="20" />
              </div>
              <div>
                <h5 class="text-sm font-bold text-slate-800 uppercase tracking-wide">Estrutura</h5>
                <p class="text-xs text-slate-500 mt-1">Portaria e elevador.</p>
              </div>
            </div>

            <div class="flex gap-4 items-start">
              <div class="p-2 bg-emerald-100 rounded-lg text-emerald-700">
                <Thermometer size="20" />
              </div>
              <div>
                <h5 class="text-sm font-bold text-slate-800 uppercase tracking-wide">Climatização</h5>
                <p class="text-xs text-slate-500 mt-1">Espaço privativo e totalmente climatizado.</p>
              </div>
            </div>

            <div class="flex gap-4 items-start">
              <div class="p-2 bg-emerald-100 rounded-lg text-emerald-700">
                <ShieldCheck size="20" />
              </div>
              <div>
                <h5 class="text-sm font-bold text-slate-800 uppercase tracking-wide">Tecnologia</h5>
                <p class="text-xs text-slate-500 mt-1">Equipamentos modernos de última geração.</p>
              </div>
            </div>
          </div>

          <div class="p-6 bg-white rounded-2xl border border-emerald-100 shadow-sm flex items-center gap-4">
            <UserCheck class="text-emerald-600" size="32" />
            <p class="text-sm text-slate-600 leading-relaxed">
              Atendimento personalizado e individual, com uma equipe qualificada pronta para receber você.
            </p>
          </div>
        </div>

        <div class="grid grid-cols-2 gap-4 order-1 lg:order-2">
          <div class="space-y-4">
            <div class="rounded-3xl overflow-hidden shadow-xl transform hover:-rotate-2 transition-all duration-500">
              <img :src="images[0].url" :alt="images[0].alt" class="w-full h-64 object-cover" />
            </div>
            <div class="rounded-3xl overflow-hidden shadow-xl">
              <img :src="images[1].url" :alt="images[1].alt" class="w-full h-44 object-cover" />
            </div>
          </div>
          <div class="pt-10 space-y-4">
            <div class="rounded-3xl overflow-hidden shadow-xl">
              <img :src="images[3].url" :alt="images[3].alt" class="w-full h-44 object-cover" />
            </div>
            <div class="rounded-3xl overflow-hidden shadow-xl transform hover:rotate-2 transition-all duration-500">
              <img :src="images[2].url" :alt="images[2].alt" class="w-full h-64 object-cover" />
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&display=swap');

.font-serif {
  font-family: 'Playfair Display', serif;
}
</style>