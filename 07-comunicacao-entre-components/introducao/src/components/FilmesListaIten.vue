<template>
  <li class="list-group-item">
    <span
      >{{ filmeTituloConcatenado }} |
      {{ ano }}</span
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

export default {
  props: {
    titulo: {
      type: String,
      required: true,
    },
    ano: {
      type: Number,
      required: true,
    },
  },
  computed: {
    filmeTituloConcatenado() {
      return `Título: ${this.titulo}`
    },
  },
  created() {
    console.log(typeof this.titulo)
  },
}
</script>
