<script setup>
import NavBar from '@/components/NavBar.vue'
import HeroArea from '@/components/HeroArea.vue'
import AboutTheEvent from '@/components/AboutTheEvent.vue'
import StatisticSection from '@/components/StatisticSection.vue'

import { onMounted } from 'vue'
import GeneralKeynoteSpeakerSection from '@/components/GeneralKeynoteSpeakerSection.vue'

onMounted(() => {
  // Initiate the wowjs
})
</script>

<template>
  <div class="container-xxl bg-white p-0" id="top">
    <div class="container-xxl position-relative p-0">
      <NavBar></NavBar>
      <HeroArea></HeroArea>
    </div>
    <AboutTheEvent></AboutTheEvent>
    <StatisticSection></StatisticSection>
    <GeneralKeynoteSpeakerSection></GeneralKeynoteSpeakerSection>
  </div>
</template>
