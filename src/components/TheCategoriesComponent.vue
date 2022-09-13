<template>
  <section :class="classes">
    <div class="px-4 border-b border-t">
      <div class="py-3 flex space-x-3 overflow-auto text-sm whitespace-nowrap max-w-screen-2xl m-auto">
        <CategoryItem
          v-for="category in categories"
          :key="category"
          :category="category"
          :is-active="category === 'All'"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
  import {computed, ref} from "vue";
  import CategoryItem from "./categories/CategoryItem.vue";

  const categories = ref([
    'All',
    'Trucks',
    'Tools',
    'Machines',
    'Engines',
    'Snow',
    'Ships',
    'Roads',
    'Tanks',
    'Building',
    'Mars',
    'Woodworking',
    'Tractors',
    'Songs',
    'TV Shows',
    'Football',
    'Planes',
    'Live',
    'Streets',
    'Math',
    'Programming',
  ])

  const props = defineProps({
    isSidebarOpen: Boolean
  })

  const classes = computed(()=>{
    return [ props.isSidebarOpen ? 'xl:pl-64' : 'md:pl-[4.5rem]', 'pt-14', 'w-full', 'fixed', 'bg-white', 'bg-opacity-95', 'z-10'];
  })

</script>

<style scoped>

</style>