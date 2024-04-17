<script setup lang="ts">
useSeoMeta({
  title: 'Login | CRM-System',
});

const name = ref('');
const email = ref('');
const password = ref('');
</script>

<template>
  <div class="w-full min-h-screen flex justify-center items-center">
    <div class="w-1/4 p-5 bg-sidebar rounded">
      <h1 class="mb-5 text-center text-2xl font-bold">Login</h1>

      <form>
        <UiInput 
          v-model="name" 
          placeholder="Name" 
          type="name" 
          class="mb-3" 
        />
        <UiInput
          v-model="email"
          placeholder="Email"
          type="email"
          class="mb-3"
        />
        <UiInput
          v-model="password"
          placeholder="Password"
          type="passwoed"
          class="mb-3"
        />
        <div class="flex justify-between items-center gap-5">
          <UiButton type="button" class="text-xs" >Login</UiButton>
          <UiButton type="button" class="text-xs underline" >Register</UiButton>
        </div>
      </form>
    </div>
  </div>
</template>
