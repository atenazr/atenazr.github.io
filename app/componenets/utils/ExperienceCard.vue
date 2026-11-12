<template>

    <div class="w-full card flex flex-col bg-white p-4">
      <div class="">
        <nuxt-icon class="text-xl lg:text-[42px] text-main-yellow" :name="icon=='teaching'? 'teaching' :icon == 'work'? 'work' :'research'" />
      </div>
      <div class="w-full flex text-xs lg:text-sm items-start justify-center" >
        <div class="w-4/5">
          <div class="flex flex-col lg:flex-row font-bold">
              <div>
                 {{ title }}
              </div>
              <div v-if="!!link" class="mx-1">
                ( <span> <a class="text-main-yellow" :href="link"> Link</a></span> )
              </div>
          </div>
          <ul class="my-2 list-disc list-inside">
            <li v-for="i in description" class="my-0.5" >
              {{ i }}
            </li>
          </ul>

          <div class="mt-2 flex flex-wrap justify-start items-center">
            <div class="text-[8px] lg:text-[10px] text-main-gray px-1 py-0.5 mx-0.5" v-for="s in skills" :key="s">
              #{{ s }}
            </div>
          </div>

          <div v-if="!!learning_more" class="text-[8px] lg:text-[10px] my-2 flex align-center justify-start">
            <div>
              To learn more about it, you can see these links
            </div>
            <a v-for="(item,i) in learning_more"
               :href="item" target="_blank" class="ml-2.5 font-bold">
              {{i+1}}. Link
            </a>
          </div>
        </div>

        <div class="w-1/5 flex flex-col">
            <div class="ml-auto text-xs font-bold">
                {{ duration }}
            </div>
        </div>

      </div>
    </div>

</template>

<script lang="ts" setup>
const props = defineProps(['icon','title','duration','description','company','images','link','skills','learning_more'])
</script>

<style scoped>

</style>