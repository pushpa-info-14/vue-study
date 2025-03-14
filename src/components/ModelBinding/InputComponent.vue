<template>
  <div class="container">
    <div>
      <label for="input">Text Input</label>
      <input type="text" v-model="textInputValue" />
      <p>
        Text Input Output: <span>{{ textInputValue }}</span>
      </p>
    </div>
  </div>
</template>

<script type="ts">
import { ref } from 'vue';

const textInputValue = ref("");
</script>
