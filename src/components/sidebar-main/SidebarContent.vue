<template>
  <SideBarMainSection>
    <ul>
      <SideBarMainNavItem icon="home" label="Home" is-active />
      <SideBarMainNavItem icon="fire" label="Trending" />
      <SideBarMainNavItem icon="collections" label="Subscriptions" />
    </ul>
  </SideBarMainSection>
  <SideBarMainSection>
    <ul>
      <SideBarMainNavItem icon="library" label="Library" />
      <SideBarMainNavItem icon="history" label="History" />
    </ul>
  </SideBarMainSection>
  <SideBarMainSection class="px-8 py-4 font-medium leading-5 border-b">
    <span class="text-sm">
      Sign in to like videos, comment, and subscribe.
    </span>
    <ButtonLogin class="focus:outline-none flex items-center px-2 py-0.5 mt-3 text-sm text-blue-700 uppercase border border-blue-700 rounded-sm"/>
  </SideBarMainSection>
  <SideBarMainSection>
    <SideBarMainSectionHeading title="Best of YouTube"/>
    <ul>
      <SideBarMainNavItem icon="music" label="Music" />
      <SideBarMainNavItem icon="sports" label="Sports" />
      <SideBarMainNavItem icon="gaming" label="Gaming" />
      <SideBarMainNavItem icon="movies" label="Movies" />
      <SideBarMainNavItem icon="news" label="News" />
      <SideBarMainNavItem icon="live" label="Live" />
      <SideBarMainNavItem icon="video360" label="360&deg; Video" />
    </ul>
  </SideBarMainSection>
  <SideBarMainSection>
    <ul>
      <SideBarMainNavItem icon="channels" label="Browse channels" />
    </ul>
  </SideBarMainSection>
  <SideBarMainSection>
    <SideBarMainSectionHeading title="More from YouTube"/>
    <ul>
      <SideBarMainNavItem icon="premium" label="YouTube Premium" />
      <SideBarMainNavItem icon="liveAnt" label="Live" />
    </ul>
  </SideBarMainSection>
  <SideBarMainSection>
    <ul>
      <SideBarMainNavItem icon="settingsG" label="Settings" />
      <SideBarMainNavItem icon="historyG" label="Report history" />
      <SideBarMainNavItem icon="helpG" label="Help" />
      <SideBarMainNavItem icon="feedG" label="Send feedback" />
    </ul>
  </SideBarMainSection>
  <SideBarMainSection class="px-6 py-4 text-xs font-semibold space-y-4">
    <TheFooter/>
  </SideBarMainSection>
</template>

<script setup>

  import SideBarMainSection from '@/components/sidebar-main/SideBarMainSection.vue';
  import SideBarMainSectionHeading from '@/components/sidebar-main/SideBarMainSectionHeading.vue';
  import SideBarMainNavItem from '@/components/sidebar-main/SideBarMainNavItem.vue';
  import ButtonLogin from '@/components/header/ButtonLogin.vue';
  import TheFooter from '@/components/sidebar-main/TheFooter.vue'

</script>

<style scoped>

</style>