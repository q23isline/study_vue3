<script setup lang="ts">
import { ref, onMounted } from 'vue'
import axios from 'axios'

interface ApiResponse {
  id: string
  name: string
}

const data = ref<ApiResponse>()
const loading = ref(true)
const error = ref<string | null>(null)

onMounted(async () => {
  try {
    const response = await axios.get<ApiResponse>('http://localhost:3000/api/users')
    data.value = response.data
  } catch (err) {
    error.value = (err as Error).message
  } finally {
    loading.value = false
  }
})
</script>

<template>
  <div>
    <h1>This is an api-connect page</h1>
    <div v-if="loading">Loading...</div>
    <div v-else-if="error">Error: {{ error }}</div>
    <div v-else>
      <ul>
        <li>{{ data?.name }}</li>
      </ul>
    </div>
  </div>
</template>
