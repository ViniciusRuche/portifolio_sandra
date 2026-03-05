<script setup>
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from '@/components/ui/accordion'

const especialidades = [
  {
    value: 'item-1',
    titulo: 'Auriculoterapia (Sementes/Agulhas)',
    descricao: 'Técnicas tradicionais e neurofisiológicas que utilizam estímulos no pavilhão auricular para alívio de dores, ansiedade e equilíbrio energético.'
  },
  {
    value: 'item-2',
    titulo: 'Auriculoterapia com Laser',
    descricao: 'Tecnologia indolor e de alta precisão. O laser de baixa intensidade acelera resultados terapêuticos sem a necessidade de agulhas.'
  },
  {
    value: 'item-3',
    titulo: 'Massoterapia & Sniper',
    descricao: 'Manobras manuais para relaxamento e a técnica Sniper para liberação de pontos de tensão específicos com máxima eficácia.'
  },
  {
    value: 'item-4',
    titulo: 'Liberação Miofascial',
    descricao: 'Tratamento focado na fáscia muscular para devolver mobilidade, tratar dores crónicas e melhorar a performance física.'
  },
  {
    value: 'item-5',
    titulo: 'Estética & Modeladora',
    descricao: 'Massagem lipomodeladora e bamboo massagem para redução de medidas, drenagem e definição da silhueta corporal.'
  }
]
</script>

<template>
  <section id="especialidades" class="py-24 bg-white">
    <div class="container mx-auto px-6 max-w-[1200px]">
      
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-16 items-start">
        
        <div class="lg:col-span-5 lg:sticky lg:top-32 space-y-6">
          <div class="relative overflow-hidden rounded-3xl shadow-2xl border border-emerald-50">
            <img 
              src="https://images.unsplash.com/photo-1589829545856-d10d557cf95f?w=800&q=80" 
              alt="Auriculoterapia Laser" 
              class="w-full h-64 lg:h-80 object-cover"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-emerald-900/40 to-transparent"></div>
            <p class="absolute bottom-6 left-6 text-white font-serif italic text-lg tracking-wide">Tecnologia Laser</p>
          </div>

          <div class="grid grid-cols-2 gap-4">
            <img 
              src="https://images.unsplash.com/photo-1589829545856-d10d557cf95f?w=800&q=80" 
              alt="Massagem Terapêutica" 
              class="w-full h-32 lg:h-40 object-cover rounded-2xl shadow-lg border border-emerald-50"
            />
            <img 
              src="https://images.unsplash.com/photo-1589829545856-d10d557cf95f?w=800&q=80" 
              alt="Auriculoterapia Sementes" 
              class="w-full h-32 lg:h-40 object-cover rounded-2xl shadow-lg border border-emerald-50"
            />
          </div>
        </div>

        <div class="lg:col-span-7 space-y-10">
          <div class="space-y-4">
            <h4 class="text-emerald-600 font-bold tracking-[0.3em] text-xs uppercase">Tratamentos Premium</h4>
            <h2 class="text-3xl md:text-4xl font-serif text-slate-800 leading-tight">
              Especialidades <span class="italic text-emerald-600 font-normal">Clínicas</span>
            </h2>
            <p class="text-slate-500 max-w-lg">
              Aliamos técnicas milenares aos mais avançados equipamentos para resultados rápidos e sem medicamentos.
            </p>
          </div>

          <Accordion type="single" collapsible class="w-full space-y-4">
            <AccordionItem 
              v-for="item in especialidades" 
              :key="item.value" 
              :value="item.value"
              :id="item.value"
              class="border border-slate-100 rounded-2xl px-4 lg:px-6 transition-all data-[state=open]:shadow-md data-[state=open]:bg-emerald-50/20 data-[state=open]:border-emerald-100 scroll-mt-24"
            >
              <AccordionTrigger class="text-slate-700 font-medium hover:text-emerald-600 hover:no-underline text-base lg:text-lg py-5 text-left leading-tight">
                {{ item.titulo }}
              </AccordionTrigger>
              <AccordionContent class="text-slate-500 leading-relaxed text-sm lg:text-base pb-6">
                {{ item.descricao }}
              </AccordionContent>
            </AccordionItem>
          </Accordion>

          <div class="pt-6">
            <a href="#contato" class="inline-flex items-center gap-2 text-emerald-600 font-bold tracking-widest text-xs border-b-2 border-emerald-200 pb-1 hover:border-emerald-600 transition-all">
              VER TODOS OS TRATAMENTOS 
              <span class="text-lg">→</span>
            </a>
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

:deep([data-radix-collection-item]) {
  text-decoration: none !important;
}
</style>