<script setup lang="ts">

</script>

<template>
  <section class="grid-container" style="min-height: 100vh">
    <LayoutSidebar />
    <div>
      <slot />
    </div>
  </section>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: 1fr 6fr;
}
</style>
