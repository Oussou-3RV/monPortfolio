<template>
  <div>
    <div class="bg-[#111827] min-h-screen">
      <navBar/>
      <heroSection/>
      <serviceSection/>
      <aboutSection/>
      <experienceSkill/>
      <latestProjectSection/>
    </div>
    
  </div>
</template>

<script setup lang="ts">
// import HeroSection from '@/components/heroSection.vue';
// import navBar from '@/components/navBar.vue';
// import aboutSection from './components/aboutSection.vue';
import { defineAsyncComponent } from 'vue';

//import component asynchronously
const navBar = defineAsyncComponent(()=>import('@/components/navBar.vue'))
const heroSection = defineAsyncComponent(()=>import('@/components/heroSection.vue'))
const serviceSection = defineAsyncComponent(()=>import('@/components/serviceSection.vue'))
const aboutSection = defineAsyncComponent(()=>import('@/components/aboutSection.vue'))
const experienceSkill = defineAsyncComponent(()=>import('@/components/experienceAndSkills.vue'))
const latestProjectSection = defineAsyncComponent(()=>import('@/components/latestProjectSection.vue'))


</script>

