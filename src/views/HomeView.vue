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
import Footer  from './components/Footer.vue'
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
    <Footer />
  </div>
</template>