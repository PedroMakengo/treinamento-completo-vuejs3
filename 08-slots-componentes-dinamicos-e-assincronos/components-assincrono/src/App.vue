<template>
  <div>
    <div class="jumbotron jumbotron-fluid">
      <div class="container">
        <h1 class="display-4">Lista de Filmes</h1>
        <p class="lead">
          Treinando comunicação entre Componentes
          no Vue
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: { FilmesLista },
  data: () => ({}),
}
</script>
