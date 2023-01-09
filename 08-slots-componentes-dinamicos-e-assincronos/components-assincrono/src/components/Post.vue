<template>
  <h2>{{ titulo }}</h2>
</template>

<script>
export default {
  name: 'PostComponent',
  props: {
    titulo: String,
  },
}
</script>
