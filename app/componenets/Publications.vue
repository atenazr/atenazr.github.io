<template>
  <div id="pub" class=" w-full text-main-dark-blue">
    <div class="w-full">
      <HeadingTitle tit="Publications" />
      <div class=" w-full py-2 xl:py-3">
          <ul class="list-disc list-inside whitespace-normal">
                <template v-for="item in publications" :key="item.id">
                  <li v-if="item.is_journal" class="whitespace-normal w-full text-xs lg:text-sm text-justify mb-1 xl:mb-2">
                    <span>
                        {{ item.authors_list + ' ' }}
                    </span>
                    <span class="italic">
                      {{ item.name }}.
                    </span>
                    <span v-if="!item.is_published">
                      Under review at
                    </span>
                    <span>
                      {{item.publisher }}.
                    </span>
                  </li>
                </template>
          </ul>

          <div class="text-xs lg:text-sm mt-4 mb-2">
            Conference papers (written in Farsi):
          </div>
            <ul class=" list-disc list-inside">
              <template v-for="item in publications" :key="item.id">
                <li v-if="!item.is_journal && !!item.is_selected" class="w-full text-sm text-justify mb-1 xl:mb-2">
                        <span>
                            {{ item.authors_list + ' ' }}
                        </span>
                    <span class="italic">
                          {{ item.name }}.
                        </span>
                    <span v-if="!item.is_published">
                          Under review at
                        </span>
                    <span>
                          {{item.publisher }}.
                        </span>
                </li>
              </template>
            </ul>
          <div class="text-[10px] lg:text-xs my-2">
            Full list of publications <span class="text-main-yellow">(<a href="https://drive.google.com/file/d/1oRcwIAGsNNsWxLK0lJfpT2p5HDW_GBPH/view?usp=sharing" target="_blank">Link</a>)</span>
          </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import HeadingTitle from "./utils/HeadingTitle.vue";
const props = defineProps(['publications'])

</script>

<style scoped>

</style>