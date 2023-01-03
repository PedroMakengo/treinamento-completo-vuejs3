<template>
  <div class="row">
    <!-- coluna 1 -->
    <div class="col-8">
      <h2>Filmes</h2>

      <ul class="list-group list-group-flush">
        <FilmesListaIten
          v-for="filme in filmes"
          :key="filme.id"
          :filme="filme"
          :class="aplicarClasseAtiva(filme)"
          @selecionarFilme="
            filmeSelecionado = $event
          "
        />
      </ul>
    </div>

    <!-- coluna 2 -->
    <div class="col-4">
      <FilmesListaItenInfo
        @editarFilme="editarFilme"
        :filme="filmeSelecionado"
        v-if="!editar"
      />
      <FilmesListaItenEditar
        :filme="filmeSelecionado"
        v-else
      />
    </div>
  </div>
</template>

<script>
import FilmesListaIten from './FilmesListaIten.vue'
import FilmesListaItenEditar from './FilmesListaItenEditar.vue'
import FilmesListaItenInfo from './FilmesListaItenInfo.vue'

export default {
  components: {
    FilmesListaIten,
    FilmesListaItenInfo,
    FilmesListaItenEditar,
  },
  data() {
    return {
      filmes: [
        {
          id: 1,
          titulo: 'Vingadores: Guerra Infinita',
          ano: 2018,
          diretor: 'Stan Lee',
        },
        {
          id: 2,
          titulo: 'Home Formiga e a Vespa',
          ano: 2018,
          diretor: 'Stan Lee',
        },
        {
          id: 3,
          titulo: 'Pantera Negra',
          ano: 2018,
          diretor: 'Stan Lee',
        },
        {
          id: 4,
          titulo: 'Deadpool 2',
          ano: 2018,
          diretor: 'Stan Lee',
        },
      ],
      filmeSelecionado: undefined,
      editar: false,
    }
  },
  methods: {
    aplicarClasseAtiva(filmeIterado) {
      return {
        active:
          this.filmeSelecionado &&
          this.filmeSelecionado.id ===
            filmeIterado.id,
      }
    },
    editarFilme(filme) {
      this.editar = true
      this.filmeSelecionado = filme
    },
    atualizarFilme(filmeAtualizado) {
      const indece = this.filmes.findIndex(
        (filme) => filme.id === filmeAtualizado.id
      )
      this.filmes.splice(
        indece,
        1,
        filmeAtualizado
      )
      this.filmeSelecionado = undefined
      this.editar = false
    },
  },
  created() {
    this.emitter.on(
      'selecionarFilme',
      (filmeSelecionado) => {
        this.filmeSelecionado = filmeSelecionado
      }
    )

    this.emitter.on(
      'atualizarFilme',
      this.atualizarFilme
    )
  },
}
</script>
