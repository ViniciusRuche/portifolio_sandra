<script setup>
import { ChevronRight, Facebook, Instagram, MessagesSquare } from 'lucide-vue-next'

const handleWhatsAppClick = () => {
  const fone = '5554999956357'
  const texto = "Olá! Gostaria de marcar um horário com você."
  const wpLink = `https://api.whatsapp.com/send?phone=${fone}&text=${encodeURIComponent(texto)}`
  
  window.open(wpLink, '_blank')
}

const handleInstagramClick = () => {
  const arroba = 'clinicasandraoliveira'
  const instaLink = `https://www.instagram.com/${arroba}`
  
  window.open(instaLink, '_blank')
}

const handleFacebookClick = () => {
  const arroba = 'sandraoliveiraauriculoterapia'
  const faceLink = `https://www.facebook.com/${arroba}`
  
  window.open(faceLink, '_blank')
}
</script>
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
            <a @click.prevent="handleInstagramClick" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-white/10 bg-white/5 hover:bg-white/10 transition-colors">
              <Instagram class="w-5 h-5 text-white" />
            </a>
            <a @click.prevent="handleFacebookClick" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-white/10 bg-white/5 hover:bg-white/10 transition-colors">
              <Facebook class="w-5 h-5 text-white" />
            </a>
            <a @click.prevent="handleWhatsAppClick" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-white/10 bg-white/5 hover:bg-white/10 transition-colors">
              <MessagesSquare class="w-5 h-5 text-white" />
            </a>
          </div>
        </div>
    </div>
  </section>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@1,400;1,500&display=swap');

.font-serif {
  font-family: 'Playfair Display', serif;
}
</style>