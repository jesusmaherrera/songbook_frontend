<template>
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" v-if="!!label" for="select">{{ label }}</label>
    <select class="w-full p-2 border-gray-300 rounded-lg shadow shadow-sm"  name="select" id="">
      <option
        v-for="(option, index) in options"
        :key="index"
        :value="option.value"
      >
        {{ option.label }}
      </option>
      
    </select>
  </div>
</template>

<script setup lang="ts">

const props = defineProps({
  label: {
    type: String,
    default: '',
  },
  options: {
    type: Array,
    default: []
  },
})
</script>

<style scoped>

</style>