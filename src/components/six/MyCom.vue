<template>
  <div style="border: 1px solid black">
    <p>{{ title }}</p>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
    },
  },
};
</script>

<style>
</style>