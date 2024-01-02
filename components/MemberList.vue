<template>
    <div>
        <h1>MemberList(defineComponent)</h1>
        <Suspense>
            <template #default>
                <AsyncMemberList />
            </template>
            <template #fallback>
                <p>Loading...</p>
            </template>
        </Suspense>

        <h1>MemberList(script setup)</h1>
        <Suspense>
            <template #default>
                <AsyncMemberListScriptSetup />
            </template>
            <template #fallback>
                <p>Loading...</p>
            </template>
        </Suspense>

        <h1>MemberList(not working)</h1>
        <Suspense>
            <template #default>
                <AsyncMemberListNotWorking />
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
const AsyncMemberListScriptSetup = defineAsyncComponent(() => import('../components/AsyncMemberListScriptSetup.vue'))
const AsyncMemberListNotWorking = defineAsyncComponent(() => import('../components/AsyncMemberListNotWorking.vue'))

</script>