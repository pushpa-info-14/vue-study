<script lang="ts">
import BasicModelBinding from '@/components/v-model/BasicModelBinding.vue'
import InputComponent from '@/components/v-model/InputComponent.vue'
import InputComponentComputed from '@/components/v-model/InputComponentComputed.vue'

export default {
  components: {
    BasicModelBinding,
    InputComponent,
    InputComponentComputed,
  },
  data() {
    return {
      inputValue1: '',
      inputValue2: '',
    }
  },
}
</script>

<template>
  <BasicModelBinding />
  <br />
  <InputComponent v-model="inputValue1" />
  <p>Input Component1 Output: {{ inputValue1 }}</p>
  <InputComponentComputed v-model="inputValue2" />
  <p>Input Component2 Output: {{ inputValue2 }}</p>
</template>
