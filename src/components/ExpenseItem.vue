<script setup>

const props = defineProps({
  item: Object
})

const emit = defineEmits(['remove'])

function remove(){
  emit('remove', props.item.id)
}

</script>

<template>

<tr>
  <td>{{ item.title }}</td>
  <td>{{ item.category }}</td>
  <td>{{ item.value }}</td>
  <td>
    <button class="vermei" @click="remove">X</button>
  </td>
</tr>

</template>