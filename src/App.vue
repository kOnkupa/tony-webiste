<script setup lang="ts">
import ReloadPrompt from './components/ReloadPrompt.vue'
import TheFooter from './layout/TheFooter.vue'
import TheNavigation from './layout/TheNavigation.vue'
const height = `calc(${window.innerHeight}px - 7.5rem)`
</script>

<template>
  <div class="bg-black">
    <the-navigation />
    <main class="main-content" :style="{minHeight: height}">
      <router-view v-slot="{ Component }">
        <transition name="fade" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
      <reload-prompt />
    </main>
    <the-footer />
  </div>
</template>
