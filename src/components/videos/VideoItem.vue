<template>
  <a href="#" class="mb-7 group">
    <VideoItemThumbnail :itemVideo="itemVideo" />
    <VideoItemInfo :itemVideo="itemVideo" />
  </a>
</template>

<script setup>
import {computed, defineProps} from "vue";
import VideoItemThumbnail from "@/components/videos/VideoItemThumbnail.vue";
import VideoItemInfo from '@/components/videos/VideoItemInfo.vue';

  const props = defineProps(['item']);

  const itemVideo = computed(()=> props.item)

</script>

<style scoped>

</style>