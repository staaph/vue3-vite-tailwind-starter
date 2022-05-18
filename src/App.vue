<script setup lang="ts">
import Navbar from '@/components/NavbarComponent.vue';
</script>

<template>
  <main class="h-screen overflow-hidden w-screen dark:bg-gray-900 bg-gray-100">
    <Navbar />
    <router-view />
  </main>
</template>
