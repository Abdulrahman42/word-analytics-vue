<script setup>
import { defineProps } from "vue";

defineProps({
  message: String,
});
</script>
<template>
  <p
    className="absolute bottom-[15px] left-[35px] text-red-500 text-sm mt-[5px] ml-[5px]"
  >
    {{ message }}
  </p>
</template>
