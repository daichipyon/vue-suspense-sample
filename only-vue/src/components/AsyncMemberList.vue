<template>
  <div class="card-wrapper">
    <li v-for="(user) in users" :key="user">{{ user }}</li>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  async setup() {
    const fetchUsers = () => {
      // 2000ms待機したのち、サンプルのUser名の配列を返す
      return new Promise<string[]>(resolve => {
        setTimeout(() => {
          resolve(['kyono', 'takeshi', 'motokatsu'])
        }, 2000)
      })
    };
    const users = await fetchUsers();

    return {
      users
    }
  }
});
</script>