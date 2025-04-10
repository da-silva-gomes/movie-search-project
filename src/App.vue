<script setup lang="ts">
import SearchResultsWrapper from './components/SearchResultsWrapper.vue'
import NavBar from './components/NavBar.vue'
import SearchInput from './components/SearchInput.vue'
import Notification from './components/icons/Notification.vue'
import Arrow from './components/icons/Arrow.vue'

    // TO REMOVE
const movies = [
  { value: 'next.js', label: 'Next.js' },
  { value: 'sveltekit', label: 'SvelteKit' },
  { value: 'nuxt', label: 'Nuxt' },
  { value: 'remix', label: 'Remix' },
  { value: 'astro', label: 'Astro' },
]

</script>

<template>
  <header>
    <NavBar>
      <template #heading><span class="font-bold">Concelead</span> <span class="text-red-600">Films</span></template>
      <div class="flex">
        <Notification />
        <div class="flex"> <!-- This should be a dropdown for profile pages / settings   |||    https://github.com/shadcn.png -->
          <Avatar class="mr-2">
            <AvatarImage src="https://github.com/shadcn.png" alt="profile picture" />
            <AvatarFallback>JG</AvatarFallback>
          </Avatar>
          <Arrow />
        </div>
      </div>
    </NavBar>
  </header>
  <main class="w-full flex flex-col items-center justify-center min-h-screen">
    <SearchInput :movies="movies" />
    <SearchResultsWrapper v-if="none" msg="Vite + Vue" />
  </main>
</template>

<style scoped />
