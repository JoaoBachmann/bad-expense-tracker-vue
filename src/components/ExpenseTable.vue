<script setup>

import ExpenseItem from './ExpenseItem.vue'

const props = defineProps({
  expenses: Array
})

const emit = defineEmits(['remove'])

function remove(id) {
  emit('remove', id)
}

</script>

<template>

<div class="panel">

<h2>Lista do dia</h2>

<table class="table">

  <thead>
    <tr>
      <th>Descricao</th>
      <th>Categoria</th>
      <th>Valor</th>
      <th></th>
    </tr>
  </thead>

  <tbody>

    <ExpenseItem
      v-for="item in expenses"
      :key="item.id"
      :item="item"
      @remove="remove"
    />

  </tbody>

</table>

</div>

</template>