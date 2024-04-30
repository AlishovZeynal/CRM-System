<script setup lang="ts">
import { v4 as uuid } from 'uuid'

useSeoMeta({
	title: 'Login | CRM-System',
})

const emailRef = ref('')
const passwordRef = ref('')
const nameRef = ref('')

const isLoadingStore = useIsLoadingStore()
const authStore = useAuthStore()
const router = useRouter()

const login = async () => {
	isLoadingStore.set(true)
	await account.createEmailPasswordSession(emailRef.value, passwordRef.value)
	const response = await account.get()
	if (response) {
		authStore.set({
			email: response.email,
			name: response.name,
			status: response.status,
		})
	}

	emailRef.value = ''
	passwordRef.value = ''
	nameRef.value = ''

	await router.push('/')
	isLoadingStore.set(false)
}

const register = async () => {
	await account.create(uuid(), emailRef.value, passwordRef.value, nameRef.value)
	await login()
}
</script>

<template>
  <div class="w-full min-h-screen flex justify-center items-center">
    <div class="w-1/4 p-5 bg-sidebar rounded">
      <h1 class="mb-5 text-center text-2xl font-bold">Login</h1>

      <form>
        <UiInput
          v-model="nameRef"
          placeholder="Name"
          type="name"
          class="mb-3"
        />
        <UiInput
          v-model="emailRef"
          placeholder="Email"
          type="email"
          class="mb-3"
        />
        <UiInput
          v-model="passwordRef"
          placeholder="Password"
          type="password"
          class="mb-3"
        />
        <div class="flex justify-between items-center gap-5">
          <UiButton 
            type="button" 
            class="text-xs" 
            @click="login"
          >
            Login
          </UiButton>
          <UiButton 
            type="button" 
            class="text-xs 
            underline" 
            @click="register"
          >
            Register
          </UiButton>
        </div>
      </form>
    </div>
  </div>
</template>
