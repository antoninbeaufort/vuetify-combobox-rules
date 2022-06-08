<template>
  <v-app>
    <v-main>
      <v-form ref="form">
        <v-combobox
          v-model="comboboxSelected"
          variant="underlined"
          :items="items"
          label="Item"
          :rules="[(v) => !!v || 'Requis']"
        />
        <v-combobox
          v-model="comboboxSelectedValues"
          variant="underlined"
          :items="items"
          label="Item"
          multiple
          :rules="[(v) => !!v || 'Requis']"
        />
        <v-combobox
          v-model="comboboxComplexSelected"
          variant="underlined"
          :items="complexItems"
          label="Item"
          :rules="[(v) => !!v || 'Requis']"
        />
        <v-combobox
          v-model="comboboxComplexSelectedValues"
          variant="underlined"
          :items="complexItems"
          label="Item"
          multiple
          :rules="[(v) => !!v || 'Requis']"
        />
        <v-btn @click="checkValidState">
          Submit
        </v-btn>
      </v-form>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
const form = ref(null)
const items = ref([
  'Item 1',
  'Item 2',
])

const complexItems = ref([
  {
    title: 'Item 1',
    value: 'item-1',
  },
  {
    title: 'Item 2',
    value: 'item-2',
  },
])

const comboboxSelected = ref(null)
const comboboxSelectedValues = ref(null)
const comboboxComplexSelected = ref(null)
const comboboxComplexSelectedValues = ref(null)

const checkValidState = () => {
  form.value.validate()
}
</script>
