<template>
    <NuxtLayout>
        <NuxtPage/>
    </NuxtLayout>
</template>


<script lang="ts" setup>

</script>


<style lang="scss">

.visually_hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    margin: -1px;
    border: 0;
    padding: 0;
    white-space: nowrap;
    clip-path: inset(100%);
    clip: rect(0 0 0 0);
    overflow: hidden;
}


[class*='__container'] {
    max-width: 1370px;
    margin: 0 auto;
    padding: 0 15px;
}

</style>