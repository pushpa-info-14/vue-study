<script lang="ts">
import GenericDropdown from '@/components/generic-dropdown/GenericDropdown.vue'
import BasicModelBinding from '@/components/v-model/BasicModelBinding.vue'
import InputComponent from '@/components/v-model/InputComponent.vue'
import InputComponentComputed from '@/components/v-model/InputComponentComputed.vue'

export default {
  components: {
    BasicModelBinding,
    InputComponent,
    InputComponentComputed,
    GenericDropdown,
  },
  data() {
    return {
      inputValue1: '',
      inputValue2: '',
      dropdownItems: [
        { label: 'User1', value: 1 },
        { label: 'User2', value: 2 },
        { label: 'User3', value: 3 },
        { label: 'User4', value: 4 },
      ],
      selectedItem: 0,
      dropdownItems2: [
        { label: 'Cat', value: 'cat' },
        { label: 'Dog', value: 'dog' },
        { label: 'Rabbit', value: 'rabbit' },
        { label: 'Parrot', value: 'parrot' },
      ],
      selectedItem2: 'none',
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

  <GenericDropdown :items="dropdownItems" v-model="selectedItem" place-holder="Select a User" />
  <p>Dropdown Output: {{ selectedItem }}</p>

  <GenericDropdown :items="dropdownItems2" v-model="selectedItem2" place-holder="Select a User" />
  <p>Dropdown Output: {{ selectedItem2 }}</p>
</template>
