<template>

    <div class="w-full card flex flex-col xl:h-[400px] bg-white p-4 xl:px-6">
      <div class="mb-1">
        <nuxt-icon class="text-[42px] text-main-yellow" :name="icon" />
      </div>
      <div class="flex flex-col md:flex-row mb-1">
        <div class=" font-semibold">
          {{ title }}
        </div>
        <div class="mt-1 md:mt-0 ml-auto text-xs font-semibold">
          {{ duration }}
        </div>
      </div>
      <div class="text-sm mb-1">
        {{ company }}
      </div>
      <p v-html="description" class="text-sm text-justify mb-1">
      </p>
      <div v-if="!!images">
<!--        {{ item.images }}-->
      </div>
      <div v-if="!!link1" class=" xl:mt-auto">
          <a class="text-sm hover:text-main-yellow font-semibold" :href="link1" target="_blank">Link</a>
      </div>
    </div>

</template>

<script lang="ts" setup>
const props = defineProps(['icon','title','duration','description','company','images','link1'])
</script>

<style scoped>

</style>