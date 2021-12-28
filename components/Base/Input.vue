<template>
  <div class="relative mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" v-if="label">{{ label }}</label>
    <slot name="left" />
    <input
      v-bind="$attrs"
      :value="modelValue"
      :placeholder="label"
      @input="$emit('update:modelValue', $event)"
      class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 focus:shadow-outline"
    />
       <!--leading-tight focus:outline-none focus:shadow-outline" id="username" type="text" placeholder="Username"> -->
  </div>
</template>

<script setup lang="ts">
defineProps({
  label: {
    type: String,
    default: '',
  },
  modelValue: {
    type: [String, Number],
    default:''
  },
})
</script>

<style scoped>

</style>