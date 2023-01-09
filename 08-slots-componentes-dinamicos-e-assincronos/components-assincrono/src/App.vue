<!-- eslint-disable vue/no-deprecated-slot-attribute -->
<template>
  <div id="app" class="container">
    <h1>Forma padrão</h1>

    <PostsLista :posts="posts" />

    <hr />

    <h1>Slots com escopo</h1>

    <PostsLista :posts="posts">
      <template v-slot="{ meuPost }">
        <h2>{{ meuPost.titulo }}</h2>
        <p>{{ meuPost.conteudo }}</p>
        <small>{{ meuPost.autor }}</small>
      </template>
    </PostsLista>
  </div>
</template>

<script>
import PostsLista from '@/components/PostsLista.vue'
export default {
  name: 'App',
  components: { PostsLista },
  data() {
    return {
      posts: [
        {
          id: 1,
          titulo: 'Components no Vue',
          conteudo:
            'Components são uma das peças mais importante no Vue',
          autor: 'Pedro Makengo',
        },
        {
          id: 2,
          titulo:
            'Distribuindo conteúdo com slots',
          conteudo:
            'Slots podem ser usados como repositórios de código HTML',
          autor: 'Pedro Makengo',
        },
      ],
    }
  },
}
</script>

<style scoped>
.container {
  width: 70%;
  margin: 30px auto;
}

/* .post-paragrafo {
  color: red;
} */
</style>
