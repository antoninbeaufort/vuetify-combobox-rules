<template>
  <v-app>
    <v-main>
      <v-form ref="form">
        Working
        <v-combobox v-model="modelWorking" :items="items" :rules="[(v) => !!v || 'Requis']" />
        Not working
        <v-combobox v-model="modelNotWorking" multiple :items="items" :rules="[(v) => !!v || 'Requis']" />
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
const modelWorking = ref(null)
const modelNotWorking = ref(null)
const items = ref([
  'Item 1',
  'Item 2',
])

const checkValidState = () => {
  form.value.validate()
}
</script>
