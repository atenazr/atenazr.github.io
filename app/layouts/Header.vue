<template>
<header class="w-full bg-secondary-white md:pt-3">
  <div class="container w-full ">
      <div class="md:hidden text-sm">
          <div @click="switchMenu" class=" md:hidden p-2 cursor-pointer">
            <nuxt-icon name="menu" class="text-main-dark-blue text-[28px]" />
          </div>
          <div @click="switchMenu"
               :class="showMenu? 'left-4 opacity-100' : 'left-[-340px] opacity-0'"
               class="w-1/3 absolute rounded-2xl overflow-hidden duration-[1.5s] ease-in-out top-[50px] border-t border-white  z-20">
            <div class="w-full">
                <div v-for="item in menus" :key="item.id" class="w-full">
                  <a class=" bg-secondary-white w-full inline-block font-bold p-4 border-b border-main-dark-blue text-main-dark-blue hover:text-main-yellow"
                      :href="item.link">
                    {{ item.name }}
                  </a>
                </div>
            </div>
          </div>
      </div>
      <div class="hidden md:flex align-center justify-center">
          <div v-for="item in menus" :key="item.id"
               class="border-transparent font-bold xl:text-sm border-b-4 hover:border-main-gray duration-[0.2s] mx-2.5 xl:mx-5 pb-2 px-1 ease-in-out  text-main-dark-blue">
            <a :href="item.link">
              {{ item.name }}
            </a>
          </div>
      </div>
  </div>
</header>
</template>

<script setup lang="ts">
import {ref} from "vue";

const showMenu = ref(false)
const switchMenu=function(){
  showMenu.value = !showMenu.value
}

const menus=[
  {
    id:0,
    name:'About',
    link:'/'
  },
  {
    id:1,
    name:'Education',
    link:'/#education'
  },
  {
    id:3,
    name:'Publications',
    link:'/#publications'
  },
  {
    id:2,
    name:'Experience',
    link:'/#experience'
  },
]

</script>

<style scoped>

</style>