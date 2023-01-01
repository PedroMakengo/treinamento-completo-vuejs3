<template>
  <li class="list-group-item">
    <span
      >{{ filme.titulo }} | {{ filme.ano }}</span
    >
    <button class="btn btn-secondary float-right">
      Selecionar
    </button>
  </li>
</template>

<script>
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

export default {
  inheritAttrs: false,
  props: {
    filme: {
      type: Object,
      required: true,
    },
  },
}
</script>
