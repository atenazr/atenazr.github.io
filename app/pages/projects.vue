<template>
  <div class="w-full ">
    <div id="projects"  class="w-full bg-secondary-white p-8" ></div>
      <div class="w-full min-h-dvh bg-secondary-white py-2 xl:py-4 px-4">
          <div class="container w-full">
            <HeadingTitle tit="Projects"  />

            <div class="w-full text-main-dark-blue flex flex-col xl:flex-row flex-wrap p-2 md:p-4">
              <div class="w-full xl:w-1/2 p-2 md:p-4 text-main-dark-blue"  v-for="item in projects" :key="item.id">

                <div class="w-full card flex flex-col xl:h-[280px] bg-white p-4 xl:px-6">
                  <div class="mb-1">
                    <nuxt-icon class="text-[42px] text-main-yellow" name="work" />
                  </div>
                  <div class="flex flex-col md:flex-row mb-1">
                    <div class=" font-semibold">
                      {{ item.title }}
                    </div>
                  </div>
                  <p v-html="item.description" class="text-sm text-justify mb-1">
                  </p>
                  <div v-if="item.link" class=" xl:mt-auto">
                    <a class="text-sm hover:text-main-yellow font-semibold" :href="item.link" target="_blank">Link</a>
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
import { projects } from "../assets/data/projects"
</script>