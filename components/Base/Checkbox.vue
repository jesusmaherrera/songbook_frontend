<template>
  <div>
    <input
      name="fieldCheckbox"
      type="checkbox"
      :checked="modelValue"
      @change="$emit('update:modelValue', $event.target.checked)"
      class="mr-2 border rounded shadow shadow-lg py-2 px-3 cursor-pointer"
    />
    <label v-if="label" for="fieldCheckbox" class="cursor-pointer">{{ label }}</label>
  </div>
</template>

<script setup lang="ts">
defineProps({
  label: {
    type: String,
    default: '',
  },
  modelValue: {
    type: Boolean,
    default: false
  }
})
</script>

<style scoped>

</style>