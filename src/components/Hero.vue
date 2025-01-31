<script setup>
import { defineProps } from "vue";

defineProps({
  title: {
    type: String,
    default: "Become a Vue Dev",
  },
  subtitle: {
    type: String,
    default: "Find the Vue Job that fits your skills and needs",
  },
});
</script>

<template>
  <section id="hero" class="bg-green-700 py-20 mb-4">
    <div class="flex flex-col items-center text-center text-white">
      <h1 class="text-4xl font-extrabold">{{ title }}</h1>
      <p class="my-4 text-xl">
        {{ subtitle }}
      </p>
    </div>
  </section>
</template>
