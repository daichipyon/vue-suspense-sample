<template>
    <div>
        <!-- usersをliタグで表示する -->
        <ul>
            <li v-for="user in users" :key="user">{{ user }}</li>
        </ul>
    </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue'

const users = ref<string[]>([])

const fetchUsers = () => {
      return new Promise<string[]>(resolve => {
        setTimeout(() => {
          resolve(['kyono', 'takeshi', 'motokatsu'])
        }, 1000)
      })
    };

onMounted( async () => {
    console.log('mounted')
    users.value = await fetchUsers()
})

</script>