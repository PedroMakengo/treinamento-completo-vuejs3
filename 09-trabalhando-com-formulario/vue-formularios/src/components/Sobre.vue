<template>
  <div>
    <h2>Sobre</h2>

    <p v-if="autor">Autor: {{ autor }}</p>
    <input type="text" v-model="autor" />
    <button v-if="btn">Adicionar</button>
  </div>
</template>

<script>
export default {
  name: 'PageSobre',
  data() {
    return {
      autor: '',
    }
  },
  created() {
    console.log('Created!')
  },
  unmounted() {
    console.log('Destroy')
  },
  activated() {
    console.log('Activated')
  },
  deactivated() {
    console.log('Deactivated')
  },
}
</script>
