<template>
  <input type="text" v-model="writableComputed" />
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
  computed: {
    writableComputed: {
      get() {
        return this.modelValue
      },
      set(value: string) {
        this.$emit('update:modelValue', value)
      },
    },
  },
}
</script>
