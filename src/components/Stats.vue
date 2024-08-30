<script setup>
import Stat from "./Stat.vue";
import { defineProps } from "vue";

const props = defineProps({
  numberOfWords: Number,
  numberOfCharacters: Number,
  instagramCharactersLeft: Number,
  facebookCharactersLeft: Number,
});
</script>
<template>
  <section className="flex flex-wrap bg-[#f1f6f8] flex-[1.3]">
    <Stat :number="numberOfWords" label="Words" />
    <Stat :number="numberOfCharacters" label="Characters" />
    <Stat :number="instagramCharactersLeft" label="Instagram" />
    <Stat :number="facebookCharactersLeft" label="Facebook" />
  </section>
</template>
