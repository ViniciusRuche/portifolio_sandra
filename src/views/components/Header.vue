<template>
  <section class="relative w-full h-screen min-h-[600px] flex items-end justify-center overflow-hidden">
    <div class="absolute inset-0 z-0">
      <img 
        src="/images/perfil.png" 
        alt="Sandra Oliveira" 
        class="w-full h-full object-cover object-center"
      />
      <div class="absolute inset-0 bg-gradient-to-r from-[#fdfaf5]/60 via-transparent to-transparent"></div>
    </div>

    <div class="pb-16 relative z-10 container mx-auto px-6 text-center flex flex-col items-center">
      
      <h1 class="font-serif text-[1.8rem] md:text-[2.5rem] lg:text-[3rem] text-white max-w-[800px] leading-tight italic">
        "A vida leve é aquela que te permite ser o que você é"
      </h1>

      <p class="mt-4 text-[0.85rem] md:text-[1rem] tracking-[0.1em] text-white font-light">
        Eu posso te ajudar com isso, vamos juntos?
      </p>

        <div class="flex flex-wrap justify-center gap-4 pt-4 animate-in fade-in slide-in-from-bottom-12 duration-1000">
          <a href="#contato" class="h-12 px-8 rounded-full bg-emerald-600 text-white font-bold hover:bg-emerald-700 hover:scale-105 transition-all flex items-center gap-2">
            AGENDE SEU HORÁRIO <ChevronRight class="w-4 h-4" />
          </a>
          
          <div class="flex gap-2">
            <a href="https://www.instagram.com/clinicasandraoliveira" target="_blank" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-white/10 bg-white/5 hover:bg-white/10 transition-colors">
              <Instagram class="w-5 h-5 text-white" />
            </a>
            <a href="https://www.facebook.com/sandraoliveiraauriculoterapia?mibextid=b06tZ0" target="_blank" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-white/10 bg-white/5 hover:bg-white/10 transition-colors">
              <Facebook class="w-5 h-5 text-white" />
            </a>
            <a href="https://wa.me/5554999956357?text=Eu%20gostaria%20de%20agendar%20um%20hor%C3%A1rio." target="_blank" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-white/10 bg-white/5 hover:bg-white/10 transition-colors">
              <MessagesSquare class="w-5 h-5 text-white" />
            </a>
          </div>
        </div>
    </div>
  </section>
</template>
<script setup>
import { ChevronRight, Facebook, Instagram, MessagesSquare } from 'lucide-vue-next'
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@1,400;1,500&display=swap');

.font-serif {
  font-family: 'Playfair Display', serif;
}
</style>