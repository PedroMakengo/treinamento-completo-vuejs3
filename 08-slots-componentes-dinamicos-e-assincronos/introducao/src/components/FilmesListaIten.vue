<template>
  <li class="list-group-item">
    <span
      >{{ filme.titulo }} | {{ filme.ano }}</span
    >
    <button
      @click="selecionar"
      class="btn btn-secondary float-right"
    >
      Selecionar
    </button>
  </li>
</template>

<script>
export default {
  props: {
    filme: {
      type: Object,
      required: true,
    },
  },

  methods: {
    selecionar(event) {
      // this.$emit('selecionarFilme', this.filme)
      console.log(event)
      this.emitter.emit(
        'selecionarFilme',
        this.filme
      )
    },
  },
}
// inheritAttrs: false,

// default: 'Vingadores',
// validator(filmeTitulo) {
//   return filmeTitulo.includes('Marvel')
// },

// computed: {
//   filmeTituloConcatenado() {
//     return `Título: ${this.filme.titulo}`
//   },
// },
// created() {
//   console.log('Attrs', this.$attrs)
// },
</script>
