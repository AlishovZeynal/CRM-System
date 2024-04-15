<script setup lang="ts">
import { MENU_DATA } from './menu.data';
</script>

<template>
  <div>
    <NuxtLink
      v-for="item in MENU_DATA"
      :key="item.name"
      :to="item.url"
      class="w-full flex items-center py-1 px-3 mb-2.5 rounded-lg hover:bg-gray-700 hover:shadow transition-all"
    >
      <Icon 
        :name="item.icon" 
        class="mr-3" 
      />
      <span>{{ item.name }}</span>
    </NuxtLink>
  </div>
</template>
