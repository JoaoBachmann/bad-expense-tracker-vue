<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add'])

const title = ref('')
const value = ref('')
const category = ref('')

function addExpense() {

  if (!title.value.trim() || !value.value.toString().trim()) {
    alert('Preencha tudo')
    return
  }

  emit('add', {
    id: Date.now(),
    title: title.value,
    value: value.value,
    category: category.value || 'other'
  })

  title.value = ''
  value.value = ''
  category.value = ''
}
</script>

<template>

<div class="panel">

  <div class="lado">
    <h2 class="mais">+</h2>
    <h2 class="tamanho">Nova despesa</h2>
  </div>

  <input v-model="title" class="input" placeholder="Descricao" />
  <input v-model="value" class="input" placeholder="Valor" />
  <input v-model="category" class="input" placeholder="Categoria" />

  <div class="row">
    <button class="small-btn" @click="addExpense">+ Adicionar</button>
  </div>

</div>

</template>