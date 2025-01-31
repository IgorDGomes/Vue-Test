<script setup>
import { TriangleAlertIcon } from "lucide-vue-next";
import { RouterLink } from "vue-router";
</script>

<template>
  <section class="text-center flex flex-col items-center justify-center h-96">
    <TriangleAlertIcon class="size-16 mb-5 text-yellow-500" />
    <h1 class="text-6xl font-bold mb-4">404 Not Found</h1>
    <p class="text-xl mb-5">This page does not exist</p>
    <RouterLink
      to="/"
      class="text-white bg-green-700 hover:bg-green-900 rounded-md px-3 py-2 mt-4"
      >Go Back</RouterLink
    >
  </section>
</template>
