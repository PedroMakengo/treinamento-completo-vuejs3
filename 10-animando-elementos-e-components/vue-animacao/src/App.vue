<template>
  <div id="app">
    <div class="jumbotron jumbotron-fluid">
      <div class="container">
        <h1 class="display-4">Animações</h1>
        <p class="lead">
          Treinando transição/animação de
          elementos/components no Vue.
        </p>
      </div>
    </div>

    <div class="container">
      <button
        class="btn btn-primary mb-3"
        @click="mostrar = !mostrar"
      >
        Alternar
      </button>

      <transition
        name="custom-classes"
        enter-active-class="animate__animated animate__tada"
        leave-active-class="animate__animated animate__bounceOutRight"
      >
        <div
          class="alert alert-primary"
          v-if="mostrar"
        >
          Animações no Vue
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mostrar: true,
    }
  },
}
</script>

<style scoped>
/* slide */
.slide-enter-active {
  animation: slide 0.7s
    cubic-bezier(0.87, 0.36, 1, 0.23);
  transition: opacity 0.7s
    cubic-bezier(0.87, 0.36, 1, 0.23);
}

.slide-leave-active {
  animation: slide 0.7s reverse;
  transition: opacity 0.7s;
}

.slide-enter-from,
.slide-leave-to {
  opacity: 0;
}

@keyframes slide {
  0% {
    transform: translateX(-100px);
  }
  to {
    transform: translateX(0px);
  }
}

/* zoom */
.zoom-leave-active,
.zoom-enter-active {
  transition: transform 0.5s;
}

.zoom-enter-from,
.zoom-leave-to {
  transform: scale(0);
}

/* fade */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
