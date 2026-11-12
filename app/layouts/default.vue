<template>
  <div class="font-inter flex flex-col lg:flex-row">
    <Sidebar />
    <div class="flex bg-secondary-white lg:h-screen lg:overflow-y-auto">
      <div class="py-6 px-10">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import Sidebar from "./Sidebar.vue"
import Header from "./Header.vue";
</script>