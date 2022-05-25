<template>
  <v-app>
    <v-main>
      <v-form ref="form">
        <v-select
          v-model="selected"
          variant="underlined"
          :items="items"
          label="Item"
          :rules="[(v) => !!v || 'Item required']"
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
const selected = ref(null)
const items = ref([
  'Item 1',
  'Item 2',
])

const checkValidState = () => {
  form.value.validate()
}
</script>
