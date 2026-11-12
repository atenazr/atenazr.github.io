<template>
  <div class="w-full">
    <div class="w-full bg-secondary-white">
      <div class="container w-full">
            <HeadingTitle tit="What I have done"  />
            <div class="w-full">
                <div class="w-full my-2 text-main-dark-blue"  v-for="item in experience" :key="item.id">

                   <ExperienceCard :icon="item.type" :title="item.position"
                    :link="item.link"
                   :description="item.description"
                   :duration="item.duration"
                   :skills="item.skills"
                   :learning_more="item.learning_more" />
                </div>
            </div>
      </div>
    </div>

  </div>
</template>

<script lang="ts" setup>
import HeadingTitle from "./utils/HeadingTitle.vue";
import ExperienceCard from "./utils/ExperienceCard.vue";

const props = defineProps(["experience"])

</script>

<style scoped>

</style>