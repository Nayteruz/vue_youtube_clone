<template>
  <div class="flex items-start mt-3">
    <img :src="`https://picsum.photos/seed/avatar${itemVideo}/68`" class="mr-3 rounded-full w-9 h-9" alt="">
    <div class="text-sm">
      <span class="font-semibold text-gray-800">Video title {{ itemVideo }}</span>
      <div class="mt-1 flex items-center">
        <span>Channel name {{ itemVideo }}</span>
        <BaseIcon name="checkVideo" class="w-3.5 h-3.5 ml-1" />
      </div>
      <div v-html="summary"></div>
    </div>
    <button
      class="-mt-1 ml-auto p-1 opacity-0 group-hover:opacity-100 text-gray-500 hover:text-gray-700 focus:outline-none">
      <BaseIcon name="dotsVertical" />
    </button>
  </div>
</template>

<script setup>
  import BaseIcon from '@/components/icons/BaseIcon.vue';
  import {computed} from "vue";

  const props = defineProps(['itemVideo']);

  const summary = computed(()=>{
    return `${props.itemVideo}K views &middot; ${props.itemVideo} ${props.itemVideo === 1 ? 'day' : 'days'} ago`
  })

</script>

<style scoped>

</style>