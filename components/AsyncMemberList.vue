<template>
  <div class="card-wrapper">
    <li v-for="(user) in users" :key="user">{{ user }}</li>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  async setup() {
    const fetchUsers = async () => {
      // 2000ms待機した後、サンプルのUser名をAPIからfetchして配列を返す
      await new Promise(resolve => setTimeout(resolve, 2000));
      const res = await fetch('https://jsonplaceholder.typicode.com/users');
      const users = await res.json();
      return users.map((user: any) => user.name);
    };
    const users = await fetchUsers();

    return {
      users
    }
  }
});
</script>