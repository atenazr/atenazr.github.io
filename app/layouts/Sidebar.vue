<template>
  <div class="lg:h-dvh lg:w-[20lvw] p-4 lg:p-8 bg-white border-main-yellow lg:shrink-0" >
      <div class="flex flex-row lg:flex-col">
          <div class="my-4 shadow-[0px_4px_25px_0px_rgba(27,39,71,0.15)] border border-[rgba(27,39,71,0.5)]
              w-[120px] md:w-[160px] xl:w-[200px] bg-center bg-cover h-[120px] md:h-[160px] xl:h-[200px] rounded-full bg-[url('/assets/images/me.png')]">
          </div>

          <div class="my-4 ml-8 lg:ml-0 flex flex-col justify-center items-start">
            <div  class="text-main-dark-blue flex justify-start items-center py-1 my-1">
              <nuxt-icon class="text-[14px] xl:text-[20px]" name="location" />
              <span class="text-[10px] lg:text-sm mx-2 ">
                Shiraz, Iran
              </span>
            </div>
            <SocialItem v-for="item in socialMedia" :key="item.id" :icon="item.icon"  :text="item.text" :link="item.link" />
          </div>
      </div>

  </div>
</template>

<script setup lang="ts">
import { socialMedia } from "../assets/data/social-media";
import SocialItem from "../componenets/utils/SocialItem.vue";
</script>

<style scoped>

</style>