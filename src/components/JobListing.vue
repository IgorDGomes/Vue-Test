<script setup>
import { MapPinIcon } from "lucide-vue-next";
import { defineProps, ref, computed } from "vue";
import { RouterLink } from "vue-router";

const props = defineProps({
  job: Object,
});

const showFullDescription = ref(false);

const toggleFullDescription = () => {
  showFullDescription.value = !showFullDescription.value;
};

const truncatedDescription = computed(() => {
  let description = props.job.description;

  if (!showFullDescription.value) {
    description = description.substring(0, 90) + "...";
  }

  return description;
});
</script>

<template>
  <div class="bg-white rounded-xl shadow-md relative">
    <div class="p-4">
      <div class="mb-6">
        <span class="text-gray-600 my-2">{{ job.type }}</span>
        <h3 class="text-xl font-bold">{{ job.title }}</h3>
      </div>
      <div class="mb-5">
        <span>{{ truncatedDescription }}</span>
        <button
          class="text-green-500 hover:text-green-600 mb-5"
          @click="toggleFullDescription"
        >
          {{ showFullDescription ? "Less" : "More" }}
        </button>
      </div>

      <h3 class="text-green-500 mb-2">{{ job.salary }}</h3>

      <div class="border border-gray-100 mb-5"></div>

      <div class="flex flex-col justify-between mb-4">
        <div class="flex gap-2 items-center text-orange-700 mb-3">
          <MapPinIcon />
          <span>{{ job.location }}</span>
        </div>
        <RouterLink
          :to="'/jobs/' + job.id"
          class="w-fit h-[36px] bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg"
          >Read More</RouterLink
        >
      </div>
    </div>
  </div>
</template>
