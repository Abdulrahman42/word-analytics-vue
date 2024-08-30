<script setup>
import { defineProps } from "vue";
const props = defineProps({
  label: String,
  number: Number,
});
</script>
<template>
  <section
    class="flex flex-col flex-[1_150px] justify-center items-center stat"
  >
    <span
      class="{`text-[#4d5457] font-semibold lg:text-[35px] text-xl mb-2.5 `}"
    >
      {{ number }}
    </span>
    <h2 class="text-sm uppercase font-medium text-[#747a7c]">{{ label }}</h2>
  </section>
</template>
