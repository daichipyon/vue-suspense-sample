<template>
  <div>
    <li v-for="user in users" :key="user">{{ user }}</li>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue'

const users = ref<string[]>([])

const fetchUsers = async () => {
  // ２０００ミリ秒待機する
  await new Promise(resolve => setTimeout(resolve, 2000))
  // String型の配列を取得して、usersに代入する
  users.value = await fetch('https://jsonplaceholder.typicode.com/users')
    .then(res => res.json())
    .then(res => res.map((user: any) => user.name))
}

onMounted( () => {
  fetchUsers()
})
</script>