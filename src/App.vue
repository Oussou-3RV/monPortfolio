<template>
  <div>
    <div class="bg-[#111827] min-h-screen">
      <navBar/>
    </div>
    
  </div>
</template>

<script setup lang="ts">
// import HeroSection from '@/components/heroSection.vue';
// import navBar from '@/components/navBar.vue';
import { defineAsyncComponent } from 'vue';

//import component asynchronously
const navBar = defineAsyncComponent(()=>import('@/components/navBar.vue'))
</script>

