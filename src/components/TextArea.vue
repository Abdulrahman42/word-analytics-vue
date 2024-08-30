<script setup>
import Warning from "./Warning.vue";
import { defineProps, ref, defineEmits, computed } from "vue";
const warningText = ref("");
defineProps({
  value: String,
});
const emit = defineEmits(["change"]);

const changeText = (e) => {
  let newText = e.target.value;
  if (newText.includes("<script>")) {
    warningText.value = "No script tag allowed!";
    newText = newText.replace("<script>", "");
  } else if (newText.includes("@")) {
    warningText.value = "No @ tag allowed!";
    newText = newText.replace("@", "");
  } else {
    warningText.value = "";
  }
  emit("change", newText);
};

const WarningMessage = computed(() => {
  return warningText;
});
</script>
<template>
  <div
    class="resize py-[30px] px-[40px] text-[22px] flex-[2] placeholder:font-medium placeholder:text-[#959c9f]"
  >
    <textarea
      @input="changeText"
      :value="value"
      class="h-full w-full"
      placeholder="Enter your text"
      :spellcheck="false"
    />
    <Warning :message="WarningMessage" />
  </div>
</template>
