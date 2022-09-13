<template>
  <Transition
    enter-from-class="opacity-0"
    enter-active-class="transition-opacity easy-linear duration-200"
    enter-to-class="opacity-100"
    leave-from-class="opacity-100"
    leave-active-class="transition-opacity easy-linear duration-200"
    leave-to-class="opacity-0"
  >
    <TheSidebarMobileOverlay v-show="isOpen" @click="close" />
  </Transition>
  <Transition
      enter-from-class="-translate-x-full"
      enter-active-class="transition easy-in-out duration-200 transform"
      enter-to-class="translate-x-0"
      leave-from-class="translate-x-0"
      leave-active-class="transition easy-in-out duration-200 transform"
      leave-to-class="-translate-x-full"
  >
    <aside @keydown.esc="close" tabindex="-1" ref="mobileSidebar" v-show="isOpen" class="w-64 max-h-screen overflow-auto bg-white fixed z-40 outline-none">
      <section class="flex items-center p-4 border-b sticky top-0 bg-white">
        <button @click="close" class="ml-2 mr-6 focus:outline-none">
          <BaseIcon name="menu"/>
        </button>
        <LogoMain/>
      </section>
      <SidebarContent/>
    </aside>
  </Transition>
</template>

<script setup>

  import TheSidebarMobileOverlay from '@/components/sidebar-main/TheSidebarMobileOverlay.vue';
  import SidebarContent from '@/components/sidebar-main/SidebarContent.vue'
  import LogoMain from '@/components/header/LogoMain.vue'
  import BaseIcon from '@/components/icons/BaseIcon.vue'
  import {ref, watch, nextTick} from "vue";

  const props = defineProps({
    isOpen: Boolean
  });
  const emit = defineEmits({
    close: null
  });

  const close = () => {
    emit('close');
  }

  const mobileSidebar = ref(null);

  watch(()=> props.isOpen, async (newVal)=>{
    await nextTick()
    newVal && mobileSidebar.value.focus();
  })

</script>

<style scoped lang="scss">
  .sidebar-enter-from {
    color: #f00;
  }
  .sidebar-enter-active{}
  .sidebar-enter-to{}

  .sidebar-leave-from{}
  .sidebar-leave-active{}
  .sidebar-leave-to{}

</style>