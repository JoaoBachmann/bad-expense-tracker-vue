<script setup>
import { ref } from 'vue'

const menuAberto = ref(false)

function toggleMenu(){
  menuAberto.value = !menuAberto.value
}
</script>

<template>
<header>
  <div class="header">

    <h1>Controle de Gastos Rapido</h1>

    <div class="menu-trigger" @click="toggleMenu">
      <div></div>
      <div></div>
      <div></div>
    </div>

    <nav class="menu-hidde" :style="{ left: menuAberto ? '0px' : '-100%' }">
      <ul>
        <li>Tudo</li>
        <li>Comida</li>
        <li>Transporte</li>
        <li>Outros</li>
      </ul>
    </nav>

  </div>
</header>
</template>