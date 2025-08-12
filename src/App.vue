<template>
  <div>
    <div class="bg-[#111827] min-h-screen">
      <navBar/>
      <heroSection/>
      <serviceSection/>
      <aboutSection/>
      <experienceSkill/>
      <latestProjectSection/>
      <BackToTop/>
    </div>
    
  </div>
</template>

<script setup lang="ts">

import { defineAsyncComponent } from 'vue';



//import component asynchronously
const navBar = defineAsyncComponent(()=>import('@/components/navBar.vue'))
const heroSection = defineAsyncComponent(()=>import('@/components/heroSection.vue'))
const serviceSection = defineAsyncComponent(()=>import('@/components/serviceSection.vue'))
const aboutSection = defineAsyncComponent(()=>import('@/components/aboutSection.vue'))
const experienceSkill = defineAsyncComponent(()=>import('@/components/experienceAndSkills.vue'))
const latestProjectSection = defineAsyncComponent(()=>import('@/components/latestProjectSection.vue'))
const BackToTop = defineAsyncComponent(()=>import('@/components/BackToTop.vue'))



</script>

