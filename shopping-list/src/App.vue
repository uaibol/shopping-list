<template>
  <h1 class="myclass">{{ header }}</h1>
  <ul>
    <li v-for="{id, label} in items" :key="id">{{ label }}</li>
  </ul>

</template>

<script setup>
import {ref} from 'vue'
const header = ref("Shopping List App")
const items = ref([
  {id: 1, label: "10 party hats"},
  {id: 2, label: "2 board games"},
  {id: 3, label: "20 caps"}
])


</script>

