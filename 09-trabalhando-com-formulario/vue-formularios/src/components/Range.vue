<template>
  <div>
    <label for="">{{ label }}</label>
    <input
      type="range"
      :value="value"
      @input="$emit('input', $event.target.value)"
    />

    {{ value }}
  </div>
</template>

<script>
export default {
  name: 'InputRange',
  props: {
    label: String,
    value: [Number, String],
  },
}
</script>
