<template>
    <NuxtLayout>
        <NuxtPage/>
    </NuxtLayout>
</template>


<script lang="ts" setup>

useSeoMeta({
  title: 'Tesla Website',
  ogTitle: 'Tesla Website',
  description: 'Tesla clone made with Nuxt3 and Tailwind CSS',
  ogDescription: 'Tesla clone made with Nuxt3 and Tailwind CSS',
  ogImage: 'https://example.com/image.png',
  twitterCard: 'summary_large_image',
})

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


</style>