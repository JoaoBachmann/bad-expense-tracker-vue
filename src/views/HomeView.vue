<script setup>
import { ref, computed } from 'vue'
import Header from '../components/Header.vue'
import AddExpense from '../components/AddExpense.vue'
import ExpenseTable from '../components/ExpenseTable.vue'

const expenses = ref([])

function addExpense(expense){
  expenses.value.push(expense)
}

function removeExpense(id){
  expenses.value = expenses.value.filter(e=>e.id!==id)
}

const total = computed(()=>{
  return expenses.value.reduce((s,i)=> s + Number(i.value || 0),0)
})
</script>

<template>

<Header />

<div class="layout">

  <AddExpense @add="addExpense" />

  <ExpenseTable
    :expenses="expenses"
    @remove="removeExpense"
  />

  <div>Total: {{ total }}</div>

</div>

</template>