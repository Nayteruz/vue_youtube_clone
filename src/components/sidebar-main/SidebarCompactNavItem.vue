<template>
  <li>
    <a href="#" :class="['flex flex-col items-center px-2 py-5 hover:bg-gray-100', {'text-red-500' : isActive}]">
      <BaseIcon :name="icon" class="w-6 h-6 mb-1.5"/>
      <span class="text-xs text-[0.7rem]">{{ label }}</span>
    </a>
  </li>
</template>


<script setup>
  import BaseIcon from '@/components/icons/BaseIcon.vue';
  import {defineProps} from "vue";
  const props = defineProps({
    label: String,
    icon: String,
    isActive: Boolean,
  });
</script>

<style scoped>

</style>