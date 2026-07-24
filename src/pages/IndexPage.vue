<template>
<div class="q-pa-md">
  <div class="q-gutter-md" style="max-width: 300px">
    <q-input v-model="text" label="Standard" />

    <q-input filled v-model="text" label="Filled" />

    <q-input outlined v-model="text" label="Outlined" />

    <q-input standout v-model="text" label="Standout" />

    <q-input
      standout="bg-teal text-white"
      v-model="text"
      label="Custom standout"
    />

    <q-input borderless v-model="text" label="Borderless" />

    <q-input rounded filled v-model="text" label="Rounded filled" />

    <q-input rounded outlined v-model="text" label="Rounded outlined" />

    <q-input rounded standout v-model="text" label="Rounded standout" />

    <q-input square filled v-model="text" label="Square filled" />

    <q-input square outlined v-model="text" label="Square outlined" />

    <q-input square standout v-model="text" label="Square standout" />
  </div>
</div></template>

<script setup>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

const $q = useQuasar()

const name = ref(null)
const age = ref(null)
const accept = ref(false)

function onSubmit() {
  if (accept.value !== true) {
    $q.notify({
      color: 'red-5',
      textColor: 'white',
      icon: 'warning',
      message: 'You need to accept the license and terms first'
    })
  } else {
    $q.notify({
      color: 'green-4',
      textColor: 'white',
      icon: 'cloud_done',
      message: 'Submitted'
    })
  }
}

function onReset() {
  name.value = null
  age.value = null
  accept.value = false
}
</script>
