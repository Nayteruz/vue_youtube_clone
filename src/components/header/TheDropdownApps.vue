<template>
  <div class="relative" ref="root">
    <button
      @click.prevent="isOpen = !isOpen"
      class="relative p-2 focus:outline-none"
    >
      <BaseIcon name="viewGrid" class="w-5 h-5" />
    </button>
    <Transition
        enter-from-class="transition opacity scale-95"
        enter-active-class="transition easy-out duration-100"
        enter-to-class="transform opacity scale-100"
        leave-from-class="transform opacity scale-100"
        leave-active-class="transition easy-it duration-75"
        leave-to-class="transform opacity scale-95"
    >
      <div class="absolute top-9 right-0 sm:left-0 bg-white w-60 border border-t-0" v-show="isOpen">
        <section class="py-2 border-b">
          <ul>
            <DropdownAppsListItem label="YouTube TV"/>
          </ul>
        </section>
        <section class="py-2 border-b">
          <ul>
            <DropdownAppsListItem label="YouTube Music"/>
            <DropdownAppsListItem label="YouTube Kids"/>
          </ul>
        </section>
        <section class="py-2">
          <ul>
            <DropdownAppsListItem label="Creator Academy"/>
            <DropdownAppsListItem label="YouTube for Artists"/>
          </ul>
        </section>
      </div>
    </Transition>
  </div>
</template>

<script setup>
  import BaseIcon from '@/components/icons/BaseIcon.vue';
  import DropdownAppsListItem from '@/components/header/DropdownAppsListItem.vue';
  import {onMounted, ref} from "vue";

  const isOpen = ref(false);
  const root = ref(null);

  onMounted(()=>{
    window.addEventListener('click', event=>{
      if(!root.value.contains(event.target)){
        isOpen.value = false;
      }
    })
  })
</script>

<style scoped>

</style>