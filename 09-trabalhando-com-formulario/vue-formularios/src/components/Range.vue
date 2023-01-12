<template>
  <div>
    <label for="">{{ label }}</label>
    <input
      type="range"
      :value="value"
      @input="
        this.$emit(
          'update:value',
          $event.target.value
        )
      "
    />
  </div>
</template>

<script>
export default {
  name: 'InputRange',
  props: {
    label: String,
    value: [Number, String],
  },

  created() {
    console.log(this.value)
  },
}
</script>
