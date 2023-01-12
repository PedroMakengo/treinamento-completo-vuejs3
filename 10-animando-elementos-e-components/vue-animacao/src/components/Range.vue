<template>
  <div>
    <label for="">{{ customLabel }}</label>
    <input
      type="range"
      :value="value"
      v-bind="$attrs"
      @input="atualizar"
      :class="inputClasses"
    />
  </div>
</template>

<script>
export default {
  name: 'InputRange',
  inheritAttrs: false,
  model: {
    prop: 'valor',
  },
  props: {
    label: String,
    valor: [Number, String],
    inputClasses: [String, Object, Array],
  },

  data() {
    return {
      valorAtual: this.value || this.$attrs.min,
    }
  },
  computed: {
    customLabel() {
      return `${this.label} (RS) ${this.valorAtual} `
    },
  },

  created() {
    console.log('Attrs', this.$attrs)
  },
  methods: {
    atualizar(event) {
      const { value } = event.target

      this.$emit('update:value', value)
      this.valorAtual = value
    },
  },
}
</script>
