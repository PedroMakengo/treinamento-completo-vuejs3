<template>
  <div>
    <h2>Lista de posts</h2>
    <PostsListaIten
      v-for="post in posts"
      :key="post.id"
      :post="post"
    >
      <slot :meuPost="post"></slot>
    </PostsListaIten>
  </div>
</template>

<script>
import PostsListaIten from '@/components/PostsListaIten.vue'
export default {
  name: 'PostLista',
  components: {
    PostsListaIten,
  },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
}
</script>
