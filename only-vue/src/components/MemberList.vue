<template>
    <div>
        <h1>MemberList</h1>
        <Suspense>
            <template #default>
                <AsyncMemberList />
            </template>
            <template #fallback>
                <p>Loading...</p>
            </template>
        </Suspense>
    </div>
</template>

<script setup lang="ts">
import { defineAsyncComponent } from 'vue'
const AsyncMemberList = defineAsyncComponent(() => import('../components/AsyncMemberList.vue'))

</script>