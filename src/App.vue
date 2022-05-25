<template>
  <v-app>
    <v-main>
      <v-form ref="form">
        <v-combobox
          v-model="selected"
          variant="underlined"
          :items="items"
          label="Item"
        />
        <v-combobox
          v-model="selectedMultiple"
          multiple
          variant="underlined"
          :items="items"
          label="Items"
        />
        <v-combobox
          v-model="selectedValue"
          variant="underlined"
          :items="complexItems"
          label="Complex item"
        />
        <v-combobox
          v-model="selectedValues"
          multiple
          variant="underlined"
          :items="complexItems"
          label="Complex items"
        />
      </v-form>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
const form = ref(null)
const selected = ref(null)
const selectedMultiple = ref(null)
const selectedValue = ref(null)
const selectedValues = ref(null)
const items = ref([
  'Item 1',
  'Item 2',
])
const complexItems = ref([
  {
    title: 'Item 1',
    value: 'item1',
  },
  {
    title: 'Item 2',
    value: 'item2',
  },
])
</script>
