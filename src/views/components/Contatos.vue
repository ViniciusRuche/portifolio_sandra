<script setup>
import { ref } from 'vue'
import { useForm } from 'vee-validate'
import * as yup from 'yup'
import { MessageCircle, Mail, MapPin, User, Send, ChevronDown } from 'lucide-vue-next'

import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'
import { Textarea } from '@/components/ui/textarea'
import {
  Select,
  SelectContent,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from '@/components/ui/select'
import {
  FormControl,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from '@/components/ui/form'

const isSuccess = ref(false)

const schema = yup.object({
  nome: yup.string().required('Seu nome é obrigatório').min(3, 'Nome muito curto'),
  servico: yup.string().required('Selecione o serviço de interesse'),
  mensagem: yup.string().required('Conte-me como posso ajudar').min(10, 'A mensagem está muito curta'),
})

const form = useForm({
  validationSchema: schema,
  initialValues: {
    nome: '',
    servico: '',
    mensagem: ''
  }
})

const onSubmit = form.handleSubmit((values) => {
  const fone = '5554999956357' 
  const texto = `Olá Sandra! Me chamo *${values.nome}*.\n\n` +
                `*Assunto:* ${values.servico}\n` +
                `*Mensagem:* ${values.mensagem}`
  
  const wpLink = `https://api.whatsapp.com/send?phone=${fone}&text=${encodeURIComponent(texto)}`
  
  window.open(wpLink, '_blank')
  isSuccess.value = true
  
  setTimeout(() => { 
    isSuccess.value = false 
    form.resetForm()
  }, 5000)
})
</script>

<template>
  <section id="contato" class="py-24 bg-white relative overflow-hidden">
    <div class="absolute bottom-0 right-0 w-[500px] h-[500px] bg-emerald-600/5 blur-[120px] rounded-full -z-10"></div>

    <div class="container mx-auto px-6">
      <div class="max-w-4xl mx-auto">
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-16">
          
          <div class="space-y-8">
            <div class="space-y-4">
              <h4 class="text-emerald-600 font-bold tracking-[0.3em] text-[10px] uppercase">Contato</h4>
              <h2 class="text-4xl font-serif text-slate-800 leading-tight">
                Vamos iniciar sua <span class="text-emerald-600 italic font-normal">jornada?</span>
              </h2>
              <p class="text-slate-500 leading-relaxed">
                Tire suas dúvidas ou agende sua consulta diretamente pelo WhatsApp. Estou localizada no Centro Comercial Metropolitan, pronta para te atender.
              </p>
            </div>

            <div class="space-y-4">
              <div class="flex items-center gap-4 text-slate-600 group">
                <div class="w-10 h-10 rounded-full bg-emerald-50 border border-emerald-100 flex items-center justify-center text-emerald-600 group-hover:bg-emerald-600 group-hover:text-white transition-colors duration-300">
                  <Mail size="18" />
                </div>
                <span class="text-sm font-medium">sandra.auriculo@gmail.com</span>
              </div>
              <div class="flex items-center gap-4 text-slate-600 group">
                <div class="w-10 h-10 rounded-full bg-emerald-50 border border-emerald-100 flex items-center justify-center text-emerald-600 group-hover:bg-emerald-600 group-hover:text-white transition-colors duration-300">
                  <MapPin size="18" />
                </div>
                <span class="text-sm font-medium italic">Rua Pinheiro Machado, Nº 2705, sala 703.</span>
              </div>
            </div>
          </div>

          <div class="relative">
            <form @submit="onSubmit" class="space-y-5 p-8 bg-slate-50 border border-emerald-50 rounded-[2.5rem] shadow-sm">
              
              <FormField v-slot="{ componentField }" name="nome">
                <FormItem class="space-y-2">
                  <FormLabel class="text-[10px] font-bold uppercase tracking-widest text-slate-400 ml-1">Seu Nome</FormLabel>
                  <FormControl>
                    <div class="relative">
                      <User class="absolute left-4 top-1/2 -translate-y-1/2 text-emerald-600/40" size="18" />
                      <Input 
                        v-bind="componentField" 
                        placeholder="Como te chamamos?" 
                        class="bg-white border-slate-100 rounded-xl py-6 pl-12 pr-4 text-slate-700 focus-visible:ring-emerald-500/20 focus-visible:border-emerald-500/50 shadow-sm"
                      />
                    </div>
                  </FormControl>
                  <FormMessage class="text-[10px] text-red-400 font-bold uppercase ml-1" />
                </FormItem>
              </FormField>

              <FormField v-slot="{ componentField }" name="servico">
                <FormItem class="space-y-2">
                  <FormLabel class="text-[10px] font-bold uppercase tracking-widest text-slate-400 ml-1">Serviço de Interesse</FormLabel>
                  <Select v-bind="componentField">
                    <FormControl>
                      <SelectTrigger class="bg-white border-slate-100 rounded-xl py-6 px-4 text-slate-700 focus:ring-emerald-500/20 focus:border-emerald-500/50 shadow-sm">
                        <SelectValue placeholder="Escolha uma opção" />
                      </SelectTrigger>
                    </FormControl>
                    <SelectContent class="bg-white border-slate-100 rounded-xl">
                      <SelectItem value="Auriculoterapia">Auriculoterapia</SelectItem>
                      <SelectItem value="Massoterapia">Massoterapia</SelectItem>
                      <SelectItem value="Liberação Miofascial">Liberação Miofascial</SelectItem>
                      <SelectItem value="Outros">Outros</SelectItem>
                    </SelectContent>
                  </Select>
                  <FormMessage class="text-[10px] text-red-400 font-bold uppercase ml-1" />
                </FormItem>
              </FormField>

              <FormField v-slot="{ componentField }" name="mensagem">
                <FormItem class="space-y-2">
                  <FormLabel class="text-[10px] font-bold uppercase tracking-widest text-slate-400 ml-1">Mensagem</FormLabel>
                  <FormControl>
                    <Textarea 
                      v-bind="componentField" 
                      rows="4" 
                      placeholder="Conte-me brevemente sobre você..."
                      class="bg-white border-slate-100 rounded-xl py-3 px-4 text-slate-700 focus-visible:ring-emerald-500/20 focus-visible:border-emerald-500/50 shadow-sm resize-none"
                    />
                  </FormControl>
                  <FormMessage class="text-[10px] text-red-400 font-bold uppercase ml-1" />
                </FormItem>
              </FormField>

              <Button 
                type="submit"
                class="w-full h-12 rounded-xl bg-emerald-600 text-white font-bold hover:bg-emerald-700 transition-all shadow-lg shadow-emerald-600/20 flex items-center justify-center gap-2 border-none"
              >
                Conversar no WhatsApp <MessageCircle size="18" />
              </Button>

              <transition name="fade">
                <div v-if="isSuccess" class="p-3 bg-emerald-50 border border-emerald-100 rounded-xl text-emerald-600 text-[11px] text-center font-bold uppercase tracking-tighter">
                  Redirecionando para o WhatsApp...
                </div>
              </transition>

            </form>
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

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>