<script setup lang="ts">
import Sun from '@/components/icons/SunIcon.vue';
import Moon from '@/components/icons/MoonIcon.vue';
import SearchIcon from '@/components/icons/SearchIcon.vue';
import { useDark } from '@/composables/useDark';
import { useHotKey } from '@/composables/useHotKey';

const { metaKey, searchbar } = useHotKey();
const { toggleTheme, userTheme } = useDark();
</script>

<template>
  <main>
    <nav
      class="w-screen h-14 dark:bg-gray-900 bg-slate-400 flex flex-row items-center px-4"
    >
      <section class="flex w-screen justify-center">
        <div class="relative flex ml-4 items-center">
          <div
            class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none"
          >
            <SearchIcon class="text-gray-400" />
          </div>
          <input
            autocomplete="off"
            ref="searchbar"
            type="text"
            class="p-2 pl-11 w-full rounded-lg text-sm input dark:border-gray-600 dark:placeholder-gray-400 focus:outline-blue-600"
            placeholder="Search..."
          />
          <div
            class="flex absolute inset-y-0 right-0 items-center pr-1 pointer-events-none gap-x-1"
          >
            <div
              class="bg-gray-900 px-1.5 py-0.5 rounded-md scale-90 text-white"
            >
              <span ref="metaKey">Meta</span>
              <span>&nbsp;+&nbsp;K</span>
            </div>
          </div>
        </div>
      </section>
      <button class="dark:text-white">
        <Sun @click="toggleTheme" v-if="userTheme === 'dark'" class="h-7 w-7" />
        <Moon v-else @click="toggleTheme" class="h-7 w-7" />
      </button>
    </nav>
  </main>
</template>
