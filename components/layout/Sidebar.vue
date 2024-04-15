<script setup lang="ts"></script>

<template>
  <aside class="w-full h-full relative px-5 py-8 bg-sidebar">
    <NuxtLink to="/" class="block mb-10">
      <NuxtImg src="/logo.svg" alt="Logo" width="100px" class="mx-auto" />
    </NuxtLink>
    <button class="absolute top-2 right-3 transition-colors hover:text-primary">
      <Icon name="line-md:logout" size="20" />
    </button>
    <LayoutMenu />
  </aside>
</template>

<style scoped></style>
