<script setup lang="ts">
useSeoMeta({
  title: 'Home | CRM-System',
});
</script>

<template>
  <div class="p-10">
    <h1 class="mb-10 text-2xl font-bold">CRM System</h1>
    <div>
      <UiCard class="mb-3" draggable="true">
        <UiCardHeader role="button">Name card</UiCardHeader>
        <UiCardContent>Company</UiCardContent>
        <UiCardFooter>Date</UiCardFooter>
      </UiCard>
    </div>
  </div>
</template>
