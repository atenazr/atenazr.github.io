<template>
  <div class="flex justify-center items-center w-full">
    <h3 class="heading-page flex-none text-center mr-4">
      {{ tit }}
    </h3>
    <div class="border-b flex-1 h-1  border-main-yellow"></div>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps(['tit'])
</script>

<style scoped>

</style>