<template lang="pug">
h1.font-bold.text-3xl.mb-5 Hello World!

.space-y-6
  .space-x-2.space-y-2(v-for='variant in variants' :key='variant')
    h2.font-bold.mb-2 {{ variant || 'default' }}
    v-btn(
      v-for='color in colors'
      :key='color'
      :color='color'
      v-bind='bindVariant(variant)'
    ) {{ color }}

  h2.font-bold.mb-2 Sizes
  .space-x-2.space-y-2(v-for='size in sizes' :key='size')
    h3.font-bold.text-sm.mb-2 {{ size }}
    v-btn(v-for='color in colors' :key='color' :color='color' :size='size') {{ color }}

  .space-x-2.space-y-2
    h2.font-bold.mb-2 Anchors
    v-btn(
      v-for='color in colors'
      :key='color'
      :color='color'
      text
      underline
      href='https://google.com'
    ) {{ color }}

  .space-x-2.space-y-2
    h2.font-bold.mb-2 Nuxt Link
    v-btn(
      v-for='color in colors'
      :key='color'
      :color='color'
      text
      underline
      :to='{ path: color }'
    ) {{ color }}

  .space-x-2.space-y-2
    h2.font-bold.mb-2 Icon
    .space-y-2(v-for='variant in iconVariants' :key='variant')
      .space-x-2.space-y-2(v-for="size in sizes" :key="size")
        v-btn(
          v-for='color in colors'
          :key='color'
          :color='color'
          :size='size'
          icon
          v-bind='bindVariant(variant)'
        )
          svg(
            xmlns='http://www.w3.org/2000/svg'
            class='h-6 w-6'
            viewBox='0 0 20 20'
            fill='currentColor'
          )
            path(d='M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z')
</template>

<script setup>
const colors = [
  "default",
  "primary",
  "secondary",
  "info",
  "warning",
  "success",
  "error",
  "dark",
];
const variants = [
  "",
  "rounded",
  "outlined",
  "text",
  "block",
  "underline",
  "disabled",
];
const iconVariants = ["", "rounded", "outlined", "text"];
const sizes = ["xxs", "xs", "sm", "md", "lg", "xl", "2xl"];
const bindVariant = (variant) => {
  return variant ? { [variant]: true } : {};
};
</script>

<style scoped>
</style>
