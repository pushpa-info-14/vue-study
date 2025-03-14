<template>
  <div class="container">
    <div>
      <label for="input">Text Input</label>
      <!-- <input type="text" v-model="textInputValue" /> -->
      <input
        type="text"
        :value="textInputValue"
        @input="textInputValue = ($event.target as HTMLInputElement).value"
      />
      <p>
        Text Input Output: <span>{{ textInputValue }}</span>
      </p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const textInputValue = ref('')
</script>
