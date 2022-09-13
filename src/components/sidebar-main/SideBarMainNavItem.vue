<template>
  <li>
    <a href="#"
       :class="classes">
      <BaseIcon :name="icon" :class="classesIcon" />
      <span>{{ label }}</span>
    </a>
  </li>
</template>

<script setup>
  import BaseIcon from '@/components/icons/BaseIcon.vue';
  import {computed} from "vue";

  const props = defineProps({
    isActive: Boolean,
    label: String,
    icon: String,
  })

  const classes = computed(()=>{
    const classes = ['flex', 'items-center', 'px-6', 'py-2', 'text-sm'];
    return props.isActive
      ? [...classes, 'font-medium', 'text-gray-800', 'bg-gray-200', 'hover:bg-gray-300']
      : [...classes, 'hover:bg-gray-100'];
  })

  const classesIcon = computed(()=>{
    const classes = ['w-6', 'h-6', 'mr-6'];
    return props.isActive
      ? [...classes, 'text-red-500']
      : [...classes];
  })

</script>

<style scoped>

</style>