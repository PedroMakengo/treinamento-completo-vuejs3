<template>
  <div>
    <h2>Filme selecionado</h2>

    <div class="card" v-if="filme">
      <div class="card-body">
        <h5 class="card-title">
          {{ filme.titulo }} | {{ filme.ano }}
        </h5>
        <button
          @click="editar"
          class="btn btn-danger float-right"
        >
          Editar
        </button>
      </div>
    </div>
    <p v-else>Nenhum filme selecionado</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      filme: undefined,
    }
  },
  created() {
    this.emitter.on(
      'selecionarFilme',
      (filmeSelecionado) => {
        this.filme = filmeSelecionado
      }
    )
  },
  methods: {
    editar(event) {
      this.$emit('editarFilme', this.filme)
      console.log(event)
    },
  },
}
</script>
