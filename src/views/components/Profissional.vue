<script setup>
import { Award, GraduationCap, CheckCircle2, Star, Briefcase } from 'lucide-vue-next'

const qualifications = [
  {
    title: 'CEO e Fundadora',
    issuer: 'Clínica Sandra Oliveira',
    category: 'Liderança',
    description: 'À frente da gestão estratégica e técnica da clínica em Caxias do Sul.'
  },
  {
    title: 'Auriculoterapeuta',
    issuer: 'Sandra Oliveira Auriculoterapia e Massoterapia',
    date: 'Desde 2020',
    category: 'Especialidade'
  },
  {
    title: 'Massoterapeuta',
    issuer: 'Sandra Oliveira Auriculoterapia e Massoterapia',
    date: 'Desde 2010',
    category: 'Formação Base'
  }
]
</script>

<template>
  <section id="qualificacao" class="py-24 bg-white">
    <div class="container mx-auto px-6">
      
      <div class="mb-16 text-center lg:text-left max-w-2xl">
        <h4 class="text-emerald-600 font-bold tracking-[0.3em] text-xs uppercase mb-2">Trajetória de Sucesso</h4>
        <h2 class="text-4xl font-serif text-slate-800 leading-tight">
          Qualificação <span class="text-emerald-600 italic font-normal">&</span> Atuação Profissional
        </h2>
        <div class="w-20 h-1 bg-emerald-600 mt-4 mx-auto lg:mx-0 rounded-full"></div>
      </div>

      <div class="grid gap-8 md:grid-cols-3">
        <div v-for="qual in qualifications" :key="qual.title" 
             class="relative p-10 bg-slate-50 border border-slate-100 rounded-[2.5rem] hover:bg-emerald-50/30 hover:border-emerald-200 transition-all duration-500 group">
          
          <div class="absolute -top-6 left-10 p-4 bg-emerald-600 rounded-2xl text-white shadow-xl shadow-emerald-600/20 group-hover:scale-110 transition-transform">
            <Briefcase v-if="qual.category === 'Liderança'" size="24" />
            <Star v-else-if="qual.category === 'Especialidade'" size="24" />
            <GraduationCap v-else size="24" />
          </div>

          <div class="mt-4 space-y-4">
            <span class="text-[10px] font-bold tracking-widest text-emerald-600/60 uppercase">{{ qual.category }}</span>
            
            <div>
              <h3 class="text-slate-800 font-bold text-xl leading-tight">
                {{ qual.title }}
              </h3>
              <p v-if="qual.date" class="text-emerald-600 font-serif italic text-sm mt-1">{{ qual.date }}</p>
            </div>

            <p class="text-slate-500 text-sm leading-relaxed">
              {{ qual.issuer }}
            </p>

            <div v-if="qual.description" class="pt-2 text-xs text-slate-400 italic">
              {{ qual.description }}
            </div>

            <div class="pt-4 flex items-center gap-2 text-emerald-500">
              <CheckCircle2 size="16" />
              <span class="text-[10px] font-bold uppercase tracking-tighter">Atuação Comprovada</span>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-20 flex flex-col items-center">
        <div class="inline-flex items-center gap-4 p-2 pl-6 bg-slate-900 rounded-full text-white">
          <span class="text-sm font-light tracking-[0.2em]">EXPERIÊNCIA CONSOLIDADA</span>
          <div class="bg-emerald-600 px-6 py-2 rounded-full font-bold text-sm">
            16 ANOS
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