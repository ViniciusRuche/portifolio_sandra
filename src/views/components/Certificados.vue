<script setup>
import { ref } from 'vue'
import { 
  Dialog, DialogContent, DialogHeader, 
  DialogTitle, DialogTrigger 
} from '@/components/ui/dialog'
import { Award, GraduationCap, Eye } from 'lucide-vue-next'

const certificates = [
  {
    title: 'Auriculoterapia Neurofisiológica',
    issuer: 'HLS Treinamentos & Unifacear',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Especialização'
  },
  {
    title: 'Mobilidade Corporal e Liberação Sniper',
    issuer: 'Allan Joseph',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Avançado'
  },
  {
    title: 'Auriculoterapia de Sucesso',
    issuer: 'HLS Treinamentos',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Formação'
  },
  {
    title: 'Anatomia Musculoesquelética',
    issuer: 'Allan Joseph',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Educação'
  },
  {
    title: 'Massagem Profissionalizante',
    issuer: 'Chronos Escola Profissionalizante',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Base'
  },
  {
    title: 'Massagem Desportiva',
    issuer: 'Allan Joseph',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Especialidade'
  },
  {
    title: 'Dor de Cabeça e Liberação Miofascial',
    issuer: 'Allan Joseph',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Tratamento'
  },
  {
    title: 'Massagem Lipomodeladora',
    issuer: 'Chronos Escola Profissionalizante',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Estética'
  },
  {
    title: 'Bamboo Massagem',
    issuer: 'Chronos Escola Profissionalizante',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Técnica'
  },
  {
    title: 'Pontos de Acupuntura Emergencial',
    issuer: 'HLS Treinamentos',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Urgência'
  }
]
</script>
<template>
  <section id="certificados" class="py-20 bg-slate-50">
    <div class="container mx-auto px-6">
      
      <div class="mb-12 text-center lg:text-left">
        <h4 class="text-emerald-600 font-bold tracking-[0.3em] text-[10px] uppercase mb-2">Qualificação Comprovada</h4>
        <h2 class="text-3xl font-serif text-slate-800 leading-tight">
          Diplomas <span class="text-emerald-600 italic font-normal">&</span> Certificações
        </h2>
        <div class="w-16 h-1 bg-emerald-600 mt-4 mx-auto lg:mx-0 rounded-full"></div>
      </div>

      <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-3">
        <Dialog v-for="cert in certificates" :key="cert.title">
          <DialogTrigger as-child>
            <div class="flex items-center gap-4 p-5 bg-white border border-slate-100 rounded-[2rem] 
                        hover:border-emerald-200 hover:shadow-lg transition-all duration-300 cursor-pointer group relative">
              
              <div class="p-3 bg-emerald-50 rounded-2xl text-emerald-600 group-hover:bg-emerald-600 group-hover:text-white transition-colors duration-500 shrink-0">
                <GraduationCap v-if="cert.category === 'Educação'" size="20" />
                <Award v-else size="20" />
              </div>

              <div class="flex-1 pr-10">
                <h3 class="text-slate-800 font-bold text-sm md:text-base leading-tight group-hover:text-emerald-700 transition-colors">
                  {{ cert.title }}
                </h3>
                <p class="text-slate-400 text-[10px] font-bold tracking-wider mt-1 uppercase">
                  {{ cert.issuer }}
                </p>
              </div>

              <div class="absolute right-5 top-1/2 -translate-y-1/2 flex items-center gap-1 opacity-40 group-hover:opacity-100 transition-opacity">
                <Eye size="12" class="text-slate-400 group-hover:text-emerald-600" />
                <span class="text-[9px] font-black text-slate-400 group-hover:text-emerald-600 uppercase italic tracking-tighter">Visualizar</span>
              </div>
            </div>
          </DialogTrigger>

          <DialogContent class="sm:max-w-[600px] bg-white rounded-[2rem] overflow-hidden p-0 border-none shadow-2xl">
            <div class="p-6 bg-emerald-600 text-white flex justify-between items-center">
              <div>
                <h2 class="font-serif italic text-xl">{{ cert.title }}</h2>
                <p class="text-emerald-100 text-[10px] tracking-widest uppercase font-bold">{{ cert.issuer }}</p>
              </div>
            </div>
            
            <div class="p-4 bg-slate-50 flex justify-center">
              <img :src="cert.image" :alt="cert.title" class="max-w-full h-auto rounded-lg shadow-md border border-white" />
            </div>
            <div class="p-6 text-center bg-white">
              <p class="text-xs text-slate-400 uppercase tracking-widest font-bold">Certificado Digitalizado Original</p>
            </div>
          </DialogContent>
        </Dialog>
      </div>

    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&display=swap');

.font-serif {
  font-family: 'Playfair Display', serif;
}

:deep(.fixed) {
  border-radius: 2rem;
}
</style>