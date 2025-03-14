<template>
  <input type="text" :value="modelValue" @input="onUpdate" />
</template>

<script lang="ts">
export default {
  props: {
    modelValue: {
      type: String,
      required: true,
    },
  },
  emits: ['update:modelValue'],
  methods: {
    onUpdate(e: Event) {
      this.$emit('update:modelValue', (e.target as HTMLInputElement).value)
    },
  },
}
</script>
