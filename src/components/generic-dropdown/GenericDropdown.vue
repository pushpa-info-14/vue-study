<template>
  <div class="dropdown">
    <button @click="isOpen = !isOpen" class="dropdown-button">
      {{ selectedLabel }}
    </button>
    <ul v-if="isOpen" class="dropdown-menu">
      <li v-for="item in items" :key="item.value" @click="selectItem(item)">
        {{ item.label }}
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import type { PropType } from 'vue'

type DropdownItem<T> = {
  label: string
  value: T
}

export default {
  props: {
    items: {
      type: Array as PropType<DropdownItem<number | string>[]>,
      required: true,
    },
    modelValue: {
      type: [Number, String],
    },
    placeHolder: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      isOpen: false,
    }
  },
  emits: ['update:modelValue'],
  methods: {
    selectItem(item: DropdownItem<number | string>) {
      console.log(item.value)
      this.$emit('update:modelValue', item.value)
      this.isOpen = false
    },
  },
  computed: {
    selectedLabel() {
      return (
        this.items.find((item) => item.value === this.modelValue)?.label ||
        this.placeHolder ||
        'Select an option'
      )
    },
  },
}
</script>
