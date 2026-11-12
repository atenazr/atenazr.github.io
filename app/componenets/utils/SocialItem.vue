<template>
  <a target="_blank" :href="link"  class="text-main-dark-blue hover:text-main-yellow duration-[0.5s] flex justify-start align-center py-1 my-1">
    <nuxt-icon class="text-[14px] lg:text-[20px]" :name="icon" />
    <span class="text-[10px] lg:text-sm mx-2 ">
          {{ text }}
    </span>
  </a>
</template>

<script setup lang="ts">
const props = defineProps(['text','link','icon'])

</script>

<style scoped>

</style>