<template>
  <div>
    <h1>client only</h1>
    <ClientOnly>
      <MemberList />
      <template #fallback>
        <p>this is rendered by serverside and will be replaced by client side</p>
      </template>

    </ClientOnly>


    <!-- <h1>not client only</h1>
    <MemberList />
     -->
  </div>
</template>
