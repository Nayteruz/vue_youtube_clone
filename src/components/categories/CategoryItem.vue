<template>
  <a
    href="#"
    :class="classes"
  >
    {{ categoryItem }}
  </a>
</template>

<script setup>
  import {computed, defineProps} from "vue";

  const props = defineProps(['category', 'isActive']);

  const categoryItem = computed(()=>props.category)

  const classes = computed(()=>{
    const cls = ['px-3', 'py-1', 'transition', 'border', 'rounded-full'];
    return props.isActive
      ? [...cls, 'bg-gray-600', 'border-gray-700', 'hover:bg-gray-500', 'text-white']
      : [...cls, 'bg-gray-100', 'border-gray-300', 'hover:bg-gray-200'];
  })

</script>

<style scoped>

</style>