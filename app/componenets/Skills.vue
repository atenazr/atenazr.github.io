<template>
  <div>
  <HeadingTitle tit="Skills" />
    <div class="w-full flex flex-wrap">
      <div class=" w-full p-2 md:p-4" v-for="item in skills" :key="item.id">
        <div class="w-full flex flex-col">
          <div class="w-[220px] rounded-2xl text-white font-semibold px-2 py-3 text-center bg-main-dark-blue text-sm md:text-md">
            {{ item.category }}
          </div>
          <div v-html="item.cat_list" class="text-sm mt-4 text-justify xl:text-base text-main-dark-blue" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import HeadingTitle from "../componenets/utils/HeadingTitle.vue";

const props = defineProps(['skills'])

</script>

<style scoped>

</style>