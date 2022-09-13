<template>
  <svg
    :class="$attrs.class ?? 'w-6 h-6'"
    fill="currentColor"
    viewBox="0 0 20 20"
    xmlns="http://www.w3.org/2000/svg"
    v-html="iconPath"
  ></svg>
</template>

<script setup>
  import {computed} from "vue";
  import icons from '@/components/icons/icons'

  const props = defineProps(['name'])

  const iconPath = computed(()=> icons[props.name])
</script>

<style scoped>

</style>