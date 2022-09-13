<template>
  <TheHeaderComponent
    @toggle-sidebar="toggleSidebar"
  />
  <TheSideBarCompact v-if="isCompactSidebarOpen"/>
  <TheSideBarMainComponent v-if="isSidebarOpen"/>
  <TheSideBarMobileComponent
    :is-open="isOpenMobileSidebar"
    @close="closeMobileSidebar"
  />
  <TheCategoriesComponent :is-sidebar-open="isSidebarOpen"/>
  <TheVideosComponent :is-sidebar-open="isSidebarOpen"/>
</template>

<script setup>

  import TheHeaderComponent from "./components/TheHeaderComponent.vue";
  import TheSideBarCompact from './components/TheSideBarCompact.vue'
  import TheSideBarMainComponent from './components/TheSideBarMainComponent.vue'
  import TheSideBarMobileComponent from './components/TheSideBarMobileComponent.vue'
  import TheCategoriesComponent from './components/TheCategoriesComponent.vue'
  import TheVideosComponent from './components/TheVideosComponent.vue'
  import {onMounted, ref} from "vue";

  const isOpenMobileSidebar = ref(false);
  const isCompactSidebarActive = ref(false);
  const isCompactSidebarOpen = ref(false);
  const isSidebarOpen = ref(false);

  const toggleSidebar = () => {
    if(window.innerWidth >=1280){
      isCompactSidebarActive.value = !isCompactSidebarActive.value;
      onResize();
    } else {
      openMobileSidebar();
    }
  }

  const openMobileSidebar = () => {
    isOpenMobileSidebar.value = true;
  }

  const closeMobileSidebar = () => {
    isOpenMobileSidebar.value = false;
  }

  const onResize = () => {
    if(window.innerWidth < 768){
      isCompactSidebarOpen.value = false;
      isSidebarOpen.value = false;
    } else if(window.innerWidth < 1280) {
      isCompactSidebarOpen.value = true;
      isSidebarOpen.value = false;
    } else {
      isCompactSidebarOpen.value = isCompactSidebarActive.value;
      isSidebarOpen.value = !isCompactSidebarActive.value;
    }
  }


  onMounted(()=>{
    if(window.innerWidth >= 768 && window.innerWidth < 1280){
      isCompactSidebarActive.value = true;
    }
    if(window.innerWidth >= 1280){
      isCompactSidebarActive.value = false;
    }
    window.addEventListener('resize', onResize)
    onResize();
  })

</script>
