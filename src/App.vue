<script setup lang="ts">
import Navbar from '@/components/NavbarComponent.vue';
</script>

<template>
  <main class="h-screen overflow-hidden w-screen">
    <Navbar />
    <router-view />
  </main>
</template>
