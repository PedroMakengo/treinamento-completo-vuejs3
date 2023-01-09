<template>
  <div id="app">
    <h1>Vue JS</h1>

    <Post titulo="Components no Vue" />
    <Post titulo="Passando dados via props" />
  </div>
</template>

<script>
import Post from '@/components/Post.vue'
export default {
  name: 'App',
  components: { Post },
}
</script>
