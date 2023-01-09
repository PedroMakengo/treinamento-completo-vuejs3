<!-- eslint-disable vue/no-deprecated-slot-attribute -->
<template>
  <div id="app" class="container">
    <h1>Vue JS</h1>

    <Post>
      <template v-slot:cabecalho>
        <h2>Components no Vue</h2>
      </template>
      <p class="post-paragrafo">
        Components são uma das peças mais
        importante no Vue
      </p>
      <span>...</span>

      <template v-slot:rodape>
        <small>por {{ autor }}</small>
      </template>
    </Post>
  </div>
</template>

<script>
import Post from '@/components/Post.vue'
export default {
  name: 'App',
  components: { Post },
  data() {
    return {
      autor: 'PedroMakengo',
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
