<script setup lang="ts">
import Exercise from '../components/Exercise.vue'
import Blog from '../components/training_sites/Blog.vue'
import ConditionModalContent from '../components/modal_content/ConditionModalContent.vue';

</script>

<template>
 <Exercise
  prompt-header="Select Second"
  :explanation-array="[
    'Write one selector that selects the second blog post',
    'without using the :nth-child or :first-child pseudo-class'
    ]"
  :correct-selectors="['.browser__page-content .Blog-post + .Blog-post']"
  :select-all="false"
  browser-url="www.music.blog"
  :modal-default-display="true"
  :allow-modal-toggle="true"
  hint="you will need to use the + operator to select the adjacent sibling of the first blog post"
  :answer-condition="{regex: /:nth-child|:first-child/, wantToMatch: true}"
  >
    <template #training-site>
      <Blog />
    </template>
    <template #modal-content>
      <ConditionModalContent />
    </template>
  </Exercise>

</template>

<style>

</style>