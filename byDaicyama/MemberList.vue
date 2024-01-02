<template>
    <div>
        <ClientOnly>
            <p>hoge</p>
            <Suspense>
                <template #default>
                    <AsyncMemberList />
                </template>
                <template #fallback>
                    <p>Loading...</p>
                </template>
            </Suspense>
        </ClientOnly>
    </div>
</template>

<script setup lang="ts">
import { defineAsyncComponent } from 'vue'
const AsyncMemberList = defineAsyncComponent(() => import('@/components/AsyncMemberList.vue'))

</script>