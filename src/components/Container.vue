<script setup>
import Stats from "./Stats.vue";
import TextArea from "./TextArea.vue";
import {
  FACEBOOK_MAX_CHARACTERS,
  INSTAGRAM_MAX_CHARACTERS,
} from "../libs/constants";
import { ref, computed } from "vue";
const text = ref("");

const numberOfWords = computed(() => {
  return text.value.split(/\s/).filter((word) => word !== "").length;
});

const numberOfCharacters = computed(() => {
  return text.value.length;
});

const instagramCharactersLeft = computed(() => {
  return INSTAGRAM_MAX_CHARACTERS - text.value.length;
});

const facebookCharactersLeft = computed(() => {
  return FACEBOOK_MAX_CHARACTERS - text.value.length;
});

const handleChange = (e) => {
  text.value = e;
};
</script>
<template>
  <main
    class="flex-col w-[85vw] lg:h-[520px] lg:w-[1050px] bg-white flex lg:flex-row mt-[55px] rounded-lg shadow-xl relative overflow-hidden"
  >
    <TextArea :value="text" @change="handleChange" />
    <Stats
      :numberOfWords="+numberOfWords"
      :numberOfCharacters="+numberOfCharacters"
      :instagramCharactersLeft="+instagramCharactersLeft"
      :facebookCharactersLeft="+facebookCharactersLeft"
    />
  </main>
</template>
