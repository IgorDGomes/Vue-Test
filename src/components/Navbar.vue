<script setup>
import { RouterLink, useRoute } from "vue-router";
import logo from "@/assets/img/logo.png";

const isActiveLink = (routePath) => {
  const route = useRoute();

  return route.path === routePath;
};
</script>

<template>
  <nav class="bg-green-700 border-b border-green-500">
    <div class="mx-auto max-w-7xl px-2">
      <div class="flex h-20 items-center justify-between">
        <div class="flex items-center justify-center">
          <RouterLink to="/" class="flex flex-shrink-0 items-center mr-4">
            <img :src="logo" alt="Vue Jobs" class="h-10 w-auto" />
            <span class="hidden md:block text-white text-2xl font-bold ml-2"
              >Vue Jobs</span
            >
          </RouterLink>
        </div>
        <ul
          class="flex items-center justify-center text-white text-lg space-x-2"
        >
          <li>
            <RouterLink
              to="/"
              :class="[
                isActiveLink('/') ? 'bg-green-900' : 'hover:bg-green-900',
                'px-3',
                'py-2',
                'rounded-md',
              ]"
              >Home</RouterLink
            >
          </li>
          <li>
            <RouterLink
              to="/jobs"
              :class="[
                isActiveLink('/jobs') ? 'bg-green-900' : 'hover:bg-green-900',
                'px-3',
                'py-2',
                'rounded-md',
              ]"
              >Jobs</RouterLink
            >
          </li>
          <li>
            <RouterLink
              to="/jobs/add"
              :class="[
                isActiveLink('/jobs/add')
                  ? 'bg-green-900'
                  : 'hover:bg-green-900',
                'px-3',
                'py-2',
                'rounded-md',
              ]"
              >Add Job</RouterLink
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
