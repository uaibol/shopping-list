<template>
  <h1 class="myclass">{{ header }}</h1>
  <input type="text" v-model="product" @keyup.enter="AddItem" placeholder="Add an item" /> <button @click="AddItem">Add</button>
  <label>
  <input type="checkbox" v-model="itemPrirority"/>
  High Priority
</label>
<label>
  <input type="checkbox" v-model="iceCreamFlovers" value="Chocalate"/>
  Chocalate
</label>
<label>
  <input type="checkbox" v-model="iceCreamFlovers" value="Vanilla"/>
  Vanilla
</label>
<label>
  <input type="checkbox" v-model="iceCreamFlovers" value="Strawery"/>
  Strawery
</label>
{{ iceCreamFlovers }}
  <br>
  {{ itemPrirority }}
  <ul>
    <li v-for="item in items" :key="item">

      {{ item.label }}
    </li>
  </ul>
</template>

<script setup>
import { ref } from 'vue'
const header = ref("Shopping List App")
const product = ref("")
const itemPrirority = ref(false)
const iceCreamFlovers = ref([])
const items = ref([
  { label: "10 party hats" },
  { label: "2 board games" },
  { label: "20 caps" }
])
const AddItem = () => {
  if (product.value.length > 0) {
    items.value.push({ label: product.value })
    product.value = ""
  }
}


</script>

