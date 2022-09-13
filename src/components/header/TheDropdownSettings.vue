<template>
  <div class="relative" ref="root">
    <button
      @click.prevent="isOpen = !isOpen"
      class="relative p-2 focus:outline-none"
    >
      <BaseIcon name="dotsVertical" class="w-5 h-5" />
    </button>
    <Transition
        enter-from-class="transition opacity scale-95"
        enter-active-class="transition easy-out duration-100"
        enter-to-class="transform opacity scale-100"
        leave-from-class="transform opacity scale-100"
        leave-active-class="transition easy-it duration-75"
        leave-to-class="transform opacity scale-95"
    >
      <div class="absolute top-9 -right-full sm:right-0 bg-white w-72 border border-t-0" v-show="isOpen">
        <section class="py-2 border-b">
          <ul>
            <DropdownSettingsListItem
                v-for="listItem in listItems.slice(0, 8)"
                :key="listItem.label"
                :icon="listItem.icon"
                :label="listItem.label"
                :with-sub-menu="listItem.withSubMenu"
            />
          </ul>
        </section>
        <section class="py-2">
          <ul>
            <DropdownSettingsListItem :label="listItems[8].label" :with-sub-menu="listItems[8].withSubMenu"/>
          </ul>
        </section>
      </div>
    </Transition>
  </div>
</template>

<script setup>
import DropdownSettingsListItem from '@/components/header/DropdownSettingsListItem.vue'
import BaseIcon from '@/components/icons/BaseIcon.vue';
import {onMounted, ref} from "vue";

const listItems = ref([
  {
    icon: 'sun',
    label: 'Appearance: Light',
    withSubMenu: true
  },
  {
    icon: 'translate',
    label: 'Language: English',
    withSubMenu: true
  },
  {
    icon: 'world',
    label: 'Location: Russia',
    withSubMenu: true
  },
  {
    icon: 'settings',
    label: 'Settings',
    withSubMenu: false
  },
  {
    icon: 'checkShield',
    label: 'Your data in YouTube',
    withSubMenu: false
  },
  {
    icon: 'help',
    label: 'Help',
    withSubMenu: false
  },
  {
    icon: 'feed',
    label: 'Send feedback',
    withSubMenu: false
  },
  {
    icon: 'calc',
    label: 'Keyboard shortcuts',
    withSubMenu: false
  },
  {
    icon: null,
    label: 'Restricted Mode: Off',
    withSubMenu: true
  }
])

const isOpen = ref(false);
const root = ref(null);

onMounted(() => {
  window.addEventListener('click', event => {
    if (!root.value.contains(event.target)){
      isOpen.value = false;
    }
  })
})

</script>

<style scoped>

</style>