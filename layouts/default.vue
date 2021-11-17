<template lang="pug">
.py-4.bg-indigo-500
  .container.mx-auto.space-x-3.text-white
    nuxt-link(to='/') Home
    nuxt-link(to='/about') About
.container.mx-auto.py-4(class='xl:p-4')
  slot
</template>

<script setup>
import { ref, toRefs } from "vue";
const props = defineProps({
  modelValue: {
    type: String,
    default: "",
  },
});
const { modelValue } = toRefs(props);
const emit = defineEmits(["update:modelValue"]);
const value = ref("");
</script>

<style scoped>
</style>
