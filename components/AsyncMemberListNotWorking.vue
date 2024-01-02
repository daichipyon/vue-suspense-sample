<template>
    <div class="card-wrapper">
      <li v-for="(user) in users" :key="user">{{ user }}</li>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue'

  const users = ref<String[]>([]);
  const fetchUsers = () => {
    // 2000ms待機したのち、サンプルのUser名の配列を返す
    return new Promise<string[]>(resolve => {
      setTimeout(() => {
        resolve(['kyono', 'takeshi', 'motokatsu'])
      }, 2000)
    })
  };

  onMounted(async () => {
    users.value = await fetchUsers();
  });
  </script>