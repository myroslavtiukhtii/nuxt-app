<template>
    <div class="
    main__home min-h-screen
    pt-32 -mt-28 grid grid-cols-1
    grid-rows-2 justify-items-center">
       <div class="main__titles opacity-80">
            <h2 class="text-5xl mb-5 text-white text-center z-30 max-sm:text-3xl">Experience Tesla</h2>
            <h3 class="text-1xl text-white text-center">Schedule a Demo Drive Todays</h3>
       </div>
        <video autoplay loop muted
            class="main__video absolute w-full h-screen object-cover top-0 left-0 -z-10">
            <source
            src="../assets/videos/Homepage-Demo-Drive-Desktop-NA.webm"
            type="video/mp4"/> Your browser does not support the video tag.
        </video>
        <button class="main__button
         z-30 rounded px-20 py-1
         border-white border-2
         text-white text-xl
         max-h-11 self-center
         max-sm:w-full max-sm:text-base
         max-sm:px-10">
         Demo drive
        </button>
    </div>
</template>

<script setup lang="ts">

</script>

<style scoped>


</style>