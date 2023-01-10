<!-- eslint-disable vue/no-deprecated-slot-attribute -->
<template>
  <div id="app" class="container">
    <h1>Components Dinâmicos</h1>

    <button
      @click="componentSelecionado = 'Home'"
    >
      Home
    </button>
    <button
      @click="componentSelecionado = 'PostsLista'"
    >
      Posts
    </button>
    <button
      @click="componentSelecionado = 'Sobre'"
    >
      Sobre
    </button>

    <keep-alive include="Sobre">
      <component
        :is="componentSelecionado"
        v-bind="propsAtuais"
      ></component>
    </keep-alive>

    <!-- Passar objetos inteiros usando a directiva v-bind -->
  </div>
</template>

<script>
import PostsLista from '@/components/PostsLista.vue'
import Home from '@/components/Home.vue'
import Sobre from '@/components/Sobre.vue'
export default {
  name: 'App',
  components: { PostsLista, Home, Sobre },
  data() {
    return {
      componentSelecionado: 'Home',
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
  computed: {
    propsAtuais() {
      return this.componentSelecionado ===
        'PostsLista'
        ? { posts: this.posts }
        : {}
    },
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
