<script setup>
import { HeartPulse, MapPin, Award, Activity } from 'lucide-vue-next'
</script>

<template>
  <section id="sobre" class="py-24 bg-white text-slate-800 overflow-hidden">
    <div class="container mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-16 items-center">
        
        <div class="lg:col-span-5 relative group">
          <div class="absolute -inset-4 bg-emerald-50 rounded-full blur-3xl opacity-70 group-hover:opacity-100 transition duration-1000"></div>
          
          <div class="relative bg-white rounded-3xl overflow-hidden shadow-2xl border border-emerald-100">
            <img 
              src="/images/sobre-mim.png" 
              alt="Sandra Oliveira" 
              class="w-full aspect-[4/5] object-cover transition-transform duration-700 group-hover:scale-105"
            />
          </div>
          
          <div class="absolute -bottom-6 -right-6 p-5 bg-white border border-emerald-100 rounded-2xl shadow-xl hidden md:block">
            <div class="flex items-center gap-4">
              <div class="p-3 bg-emerald-600 rounded-xl text-white">
                <Award size="24" />
              </div>
              <div>
                <p class="text-[10px] uppercase tracking-[0.2em] font-bold text-emerald-600">Experiência</p>
                <p class="text-sm font-bold text-slate-700">16 Anos de Atuação</p>
              </div>
            </div>
          </div>
        </div>

        <div class="lg:col-span-7 space-y-8">
          <div class="space-y-4">
            <h4 class="text-emerald-600 font-bold tracking-[0.3em] text-xs uppercase">Conheça a profissional</h4>
            <h2 class="text-3xl md:text-4xl font-serif text-slate-800 leading-tight">
              Sou a <span class="text-emerald-600 italic">Sandra Oliveira</span>, <br/>
              CEO e Fundadora da Clínica.
            </h2>
            <div class="w-20 h-1.5 bg-emerald-600 rounded-full"></div>
          </div>

          <div class="space-y-6 text-slate-600 text-lg leading-relaxed">
            <p>
              Sou <span class="text-slate-900 font-semibold">auriculoterapeuta neurofisiológica e massoterapeuta</span>. 
              Atuo na região da Serra Gaúcha, especificamente em Caxias do Sul, onde resido.
            </p>
            
            <p>
              Com 16 anos de especialização, utilizo os métodos mais avançados, como sementes, agulhas e <span class="text-emerald-600 font-medium italic">aplicações a laser</span>, focando em resultados rápidos e duradouros sem o uso de medicamentos.
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 pt-4">
            <div class="p-5 rounded-2xl border border-emerald-50 bg-emerald-50/30 flex gap-4 items-start hover:border-emerald-200 transition-colors">
              <HeartPulse class="text-emerald-600 shrink-0" size="24" />
              <div>
                <h4 class="text-sm font-bold text-slate-800 uppercase tracking-wider">Auriculoterapia</h4>
                <p class="text-xs text-slate-500 mt-1 leading-relaxed">Técnicas neurofisiológicas com uso de laser e métodos tradicionais.</p>
              </div>
            </div>

            <div class="p-5 rounded-2xl border border-emerald-50 bg-emerald-50/30 flex gap-4 items-start hover:border-emerald-200 transition-colors">
              <Activity class="text-emerald-600 shrink-0" size="24" />
              <div>
                <h4 class="text-sm font-bold text-slate-800 uppercase tracking-wider">Massoterapia</h4>
                <p class="text-xs text-slate-500 mt-1 leading-relaxed">Recuperação muscular, desportiva e Liberação Sniper.</p>
              </div>
            </div>
          </div>

          <div class="flex items-center gap-3 text-sm text-slate-400 font-medium pt-4">
            <div class="w-8 h-8 rounded-full bg-slate-100 flex items-center justify-center text-emerald-600">
              <MapPin size="16" />
            </div>
            <span>Caxias do Sul, Serra Gaúcha - RS</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&display=swap');

.font-serif {
  font-family: 'Playfair Display', serif;
}
</style>