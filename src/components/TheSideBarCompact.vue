<template>
  <aside :class="classes">
    <section>
      <ul>
        <SidebarCompactNavItem
          v-for="navItem in navItems"
          :key="navItem.label"
          :label="navItem.label"
          :icon="navItem.icon"
          :is-active="navItem.isActive"
        />
      </ul>
    </section>
  </aside>
</template>

<script setup>
import {computed, ref} from "vue";
  import SidebarCompactNavItem from '@/components/sidebar-main/SidebarCompactNavItem.vue';

  const classes = computed(()=>{
    return ['w-[4.5rem]', 'min-h-screen', 'overflow-auto', 'fixed', 'top-0', 'pt-14', 'bg-white', 'z-20'];
  })

  const navItems = ref([
    {label:'Home', icon:'home', isActive:true},
    {label:'Trending', icon:'fire', isActive:false},
    {label:'Subscriptions', icon:'collections', isActive:false},
    {label:'Library', icon:'library', isActive:false},
    {label:'History', icon:'history', isActive:false},
  ])

</script>

<style scoped lang="scss">

</style>