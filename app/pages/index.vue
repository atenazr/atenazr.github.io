<template>
  <div class="w-full py-2 bg-secondary-white">
          <HeadingTitle tit="About"  />
          <div  id="about" class="py-4 w-full">
            <p v-html="personalData.about" class="text-main-dark-blue text-xs lg:text-sm text-justify">
            </p>

          </div>

          <div>
            <HeadingTitle tit="News" />
            <div v-for="i in news" :key="i.content" class="w-full my-2 text-xs lg:text-sm text-main-dark-blue flex">
              <span class="w-28">
                {{ i.date }}
              </span>
              <span>
                {{ i.content }}
              </span>
            </div>
          </div>


          <div  class=" w-full ">
            <education :education="education"  />
          </div>

          <publications :publications="publications" />

          <experience :experience="experience" />

          <div class="mt-8 text-[10px] lg:text-xs text-main-gray">
             This portfolio was developed using Nuxt,js, Tailwind CSS, and supabase as the API server (<a class="text-main-yellow" href="https://github.com/atenazr/atenazr.github.io">Link</a>).<br>Last updated November 2026
          </div>
  </div>
</template>

<script setup lang="ts">
import { personalData } from "../assets/data/personal-data";
import HeadingTitle from "../componenets/utils/HeadingTitle.vue";
import Publications from "../componenets/Publications.vue";

import { createClient } from '@supabase/supabase-js'
import Education from "../componenets/Education.vue";
import Experience from "../componenets/Experience.vue";

const config = useRuntimeConfig()
const supabase = createClient(config.public.supabaseUrl, config.public.supabaseKey)

interface NewsItem {
  date: string
  content: string
}

const education = ref<any[]>([])
const publications = ref<any[]>([])
const experience = ref<any[]>([])
const news = ref<NewsItem[]>([])

async function getEducation() {
  const { data, error } = await supabase.from('education').select('*')
  if (error) throw error
  if(!!data){
    education.value = data
  }
}

async function getPublications() {
  const {data, error} = await supabase.from('publications').select('*')
  if (error) throw error
  if (!!data) {
    publications.value = data
  }
}

async function getExp() {
  const {data, error} = await supabase.from('experience').select('*').order('id')
  if (error) throw error
  if (!!data) {
    experience.value = data.reverse();
  }
}

async function getNews() {
  const {data, error} = await supabase.from('news').select('*')
  if (error) throw error
  if (!!data) {
    news.value = data;
  }
}

await getNews()
await getEducation()
await getPublications()
await getExp()
</script>

<style scoped>
</style>