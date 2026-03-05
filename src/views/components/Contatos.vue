<script setup>
import { useForm } from 'vee-validate'
import * as yup from 'yup'
import { MessageCircle, Mail, MapPin, User, Send } from 'lucide-vue-next'
import { ref } from 'vue'

const isSuccess = ref(false)

// Schema de validação adaptado
const schema = yup.object({
  nome: yup.string().required('Seu nome é obrigatório').min(3, 'Nome muito curto'),
  servico: yup.string().required('Selecione o serviço de interesse'),
  mensagem: yup.string().required('Conte-me como posso ajudar').min(10, 'A mensagem está muito curta'),
})

const { defineField, handleSubmit, errors, resetForm } = useForm({
  validationSchema: schema,
})

const [nome, nomeProps] = defineField('nome')
const [servico, servicoProps] = defineField('servico')
const [mensagem, mensagemProps] = defineField('mensagem')

const onSubmit = handleSubmit((values) => {
  const fone = '5554999956357' 
  const texto = `Olá Sandra! Me chamo *${values.nome}*.\n\n` +
                `*Assunto:* ${values.servico}\n` +
                `*Mensagem:* ${values.mensagem}`
  
  const wpLink = `https://api.whatsapp.com/send?phone=${fone}&text=${encodeURIComponent(texto)}`
  
  window.open(wpLink, '_blank')
  isSuccess.value = true
  resetForm()
  
  setTimeout(() => { isSuccess.value = false }, 5000)
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
              <h4 class="text-emerald-600 font-bold tracking-[0.3em] text-xs uppercase">Contato</h4>
              <h2 class="text-4xl font-serif text-slate-800 leading-tight">
                Vamos iniciar sua <span class="text-emerald-600 italic font-normal">jornada?</span>
              </h2>
              <p class="text-slate-500 leading-relaxed">
                Tire suas dúvidas ou agende sua consulta diretamente pelo WhatsApp. Estou localizada no Centro Comercial Metropolitan, pronta para te atender.
              </p>
            </div>

            <div class="space-y-4">
              <div class="flex items-center gap-4 text-slate-600">
                <div class="w-10 h-10 rounded-full bg-emerald-50 border border-emerald-100 flex items-center justify-center text-emerald-600">
                  <Mail size="18" />
                </div>
                <span class="text-sm font-medium">sandra.auriculo@gmail.com</span>
              </div>
              <div class="flex items-center gap-4 text-slate-600">
                <div class="w-10 h-10 rounded-full bg-emerald-50 border border-emerald-100 flex items-center justify-center text-emerald-600">
                  <MapPin size="18" />
                </div>
                <span class="text-sm font-medium italic">Rua Pinheiro Machado, Nº 2705, sala 703.</span>
              </div>
            </div>
          </div>

          <div class="relative">
            <form @submit="onSubmit" class="space-y-5 p-8 bg-slate-50 border border-emerald-50 rounded-[2.5rem] shadow-sm">
              
              <div class="space-y-2">
                <label class="text-[10px] font-bold uppercase tracking-widest text-slate-400 ml-1">Seu Nome</label>
                <div class="relative">
                  <User class="absolute left-4 top-1/2 -translate-y-1/2 text-emerald-600/40" size="18" />
                  <input v-model="nome" v-bind="nomeProps" type="text" placeholder="Como te chamamos?"
                    class="w-full bg-white border border-slate-100 rounded-xl py-3 pl-12 pr-4 text-slate-700 focus:outline-none focus:border-emerald-500/50 transition-all shadow-sm" />
                </div>
                <span class="text-[10px] text-red-400 font-bold uppercase ml-1">{{ errors.nome }}</span>
              </div>

              <div class="space-y-2">
                <label class="text-[10px] font-bold uppercase tracking-widest text-slate-400 ml-1">Serviço de Interesse</label>
                <select v-model="servico" v-bind="servicoProps" 
                  class="w-full bg-white border border-slate-100 rounded-xl py-3 px-4 text-slate-700 focus:outline-none focus:border-emerald-500/50 transition-all shadow-sm appearance-none">
                  <option value="" disabled selected>Escolha uma opção</option>
                  <option value="Auriculoterapia">Auriculoterapia</option>
                  <option value="Massoterapia">Massoterapia</option>
                  <option value="Liberação Miofascial">Liberação Miofascial</option>
                  <option value="Outros">Outros</option>
                </select>
                <span class="text-[10px] text-red-400 font-bold uppercase ml-1">{{ errors.servico }}</span>
              </div>

              <div class="space-y-2">
                <label class="text-[10px] font-bold uppercase tracking-widest text-slate-400 ml-1">Mensagem</label>
                <textarea v-model="mensagem" v-bind="mensagemProps" rows="4" placeholder="Conte-me brevemente sobre você..."
                  class="w-full bg-white border border-slate-100 rounded-xl py-3 px-4 text-slate-700 focus:outline-none focus:border-emerald-500/50 transition-all resize-none shadow-sm"></textarea>
                <span class="text-[10px] text-red-400 font-bold uppercase ml-1">{{ errors.mensagem }}</span>
              </div>

              <button type="submit"
                class="w-full h-12 rounded-xl bg-emerald-600 text-white font-bold hover:bg-emerald-700 transition-all shadow-lg shadow-emerald-600/20 flex items-center justify-center gap-2">
                Conversar no WhatsApp <MessageCircle size="18" />
              </button>

              <div v-if="isSuccess" class="p-3 bg-emerald-50 border border-emerald-100 rounded-xl text-emerald-600 text-sm text-center font-bold">
                Redirecionando para o WhatsApp...
              </div>

            </form>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&display=swap');
.font-serif { font-family: 'Playfair Display', serif; }
</style>