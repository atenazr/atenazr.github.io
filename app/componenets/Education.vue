<template>
  <div class="flex flex-col justify-center items-center">
    <HeadingTitle tit="Education" />
    <div class="flex flex-wrap justify-start align-center">
      <div class="w-full lg:w-1/2 p-2 text-main-dark-blue" v-for="item in education" :key="item.id">

        <div class="card py-2 px-3 xl:px-6 flex flex-col justify-center items-start">
          <div class="mb-2">
            <nuxt-icon class="text-xl lg:text-[28px] text-main-yellow" name="book" />
          </div>
          <div class="flex flex-col md:flex-row text-sm xl:text-base w-full mb-2">
            <div class="text-[10px] lg:text-xs lg:text-sm font-semibold">
              {{ item.degree }}
            </div>
            <div class="mt-2 md:mt-0 ml-auto text-[10px] lg:text-xs">
              {{ item.duration }}
            </div>
          </div>

          <div class="text-[10px] lg:text-xs flex mb-1 w-full">
            <div class="">
              {{ item.institution }}
            </div>
            <div class=" ml-auto font-semibold">
              GPA:
              {{ item.gpa }}
            </div>
          </div>

          <div  class="w-full lg:h-[140px] flex flex-col ">
            <div class="my-1">
              <div class="text-xs lg:text-sm font-semibold">
                Courses:
              </div>
              <div class="text-[10px] lg:text-xs text-justify">
                {{ item.courses }}
              </div>
            </div>

            <div class=" flex flex-col text-xs lg:text-sm my-1">
              <div class="font-semibold mr-1">
                Thesis:
              </div>
              <div class="text-[10px] lg:text-xs">
                {{ item.thesis }}
              </div>
            </div>
            <div v-if="!!item.thesisdescription" class="text-xs lg:text-sm text-justify">
              {{ item.thesisdescription }}
            </div>
            <div class="flex text-[10px] lg:text-xs my-1 mb-2">
              <div class="mr-1">
                Supervisors:
              </div>
              <div>
                {{ item.supervisors }}
              </div>
            </div>

          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import HeadingTitle from "../componenets/utils/HeadingTitle.vue";

const props = defineProps(['education'])
</script>

<style scoped>

</style>