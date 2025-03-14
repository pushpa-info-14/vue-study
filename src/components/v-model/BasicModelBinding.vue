<script setup lang="ts">
import { ref } from 'vue'

const textInputValue = ref('')

const checkboxInputValue = ref()
const checkboxTrueValue = ref('dynamic yes')
const checkboxFalseValue = ref('dynamic no')

const radioInputValue = ref()
const radioInputValueOne = ref('dynamic one')
const radioInputValueTwo = ref('dynamic two')

const selectInputValue = ref()
</script>

<template>
  <div class="container">
    <div>
      <label>Text Input</label>
      <input type="text" v-model="textInputValue" />
      <!-- <input
        type="text"
        :value="textInputValue"
        @input="textInputValue = ($event.target as HTMLInputElement).value"
      /> -->
      <p>
        Text Input Output: <span>{{ textInputValue }}</span>
      </p>
      <br />

      <label>Checkbox Input</label>
      <input
        type="checkbox"
        v-model="checkboxInputValue"
        :true-value="checkboxTrueValue"
        :false-value="checkboxFalseValue"
      />
      <p>
        Checkbox Input Output: <span>{{ checkboxInputValue }}</span>
      </p>
      <br />

      <label>Radio Input</label>
      <input type="radio" v-model="radioInputValue" :value="radioInputValueOne" />
      <input type="radio" v-model="radioInputValue" :value="radioInputValueTwo" />
      <p>
        Radio Input Output: <span>{{ radioInputValue }}</span>
      </p>
      <br />

      <label>Select Input</label>
      <select v-model="selectInputValue">
        <option value="option 1">Option 1</option>
        <option :value="{ option: 2, value: 5 }">Option 2</option>
      </select>
      <p>
        Select Input Output: <span>{{ selectInputValue }}</span>
      </p>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  gap: 32px;
}
</style>
