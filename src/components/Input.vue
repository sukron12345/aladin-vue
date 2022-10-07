<script setup lang="ts">
import { ref } from "vue";

defineProps({
  type: String,
  name: String,
  number: String,
  label: String,
  placeholder: String,
});

const isValid = ref();

const handleInput = (e: any) => {
  const input = e.target.value;
  if (!input) {
    isValid.value = false;
    return;
  }

  isValid.value = true;
};
</script>

<template>
  <li class="group z-10 flex w-full gap-8">
    <div class="flex flex-col w-full gap-2">
      <label for="name" class="font-medium text-bg">{{ label }}</label>
      <input
        :autocomplete="type"
        :type="type"
        :name="name"
        class="w-full px-4 py-2 outline-none border-none rounded bg-text text-base text-bg placeholder:text-fgVar transition-all ring-transparent ring-1 focus:ring-primary"
        :class="{ 'outline-offset-0 outline-1 outline-primary': isValid }"
        @blur="handleInput"
        onchange="onchange"
      />
    </div>
  </li>
</template>
