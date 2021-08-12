<template>
  <div class="q-pa-md" style="max-width: 400px">
    <h4>Entrada de veículo</h4>
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
     <q-input
        filled
        v-model="modelo"
        label="Modelo"
        hint=""
      />
      <q-input
        filled
        v-model="cor"
        label="Cor"
        hint=""
      />
      <q-input
        filled
        v-model="placa"
        label="Placa do carro"
        hint=""
      />

      <q-input
        filled
        type="time"
        v-model="time"
        label="Hora de entrada"
        lazy-rules
      />

      <!-- <q-toggle v-model="accept" label="I accept the license and terms" /> -->

      <div>
        <q-btn label="Registrar" type="submit" color="primary"/>
        <q-btn label="Cancelar" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>

  </div>
</template>
<script>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default {
  setup () {
    const $q = useQuasar()

    const name = ref(null)
    const age = ref(null)
    const accept = ref(false)

    return {
      name,
      age,
      accept,

      onSubmit () {
        $q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Veículo registrado com sucesso!'
        })
      },

      onReset () {
        name.value = null
        age.value = null
        accept.value = false
      }
    }
  }
}
</script>
