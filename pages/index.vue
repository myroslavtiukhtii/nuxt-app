<template>
    <section class="hero pt-32 -mt-28 relative">
        <div class="hero__container
            grid grid-cols-1
            grid-rows-2 justify-items-center">
            <div class="hero__titles opacity-80">
                <h2 class="text-5xl mb-5 text-white text-center z-30 max-sm:text-3xl">Experience Tesla</h2>
                <h3 class="text-1xl text-white text-center">Schedule a Demo Drive Todays</h3>
            </div>
            <video autoplay loop muted
                class="hero__video absolute w-full h-full object-cover top-0 left-0 -z-10">
                <source
                src="../assets/videos/Homepage-Demo-Drive-Desktop-NA.webm"
                type="video/mp4"/> Your browser does not support the video tag.
            </video>
            <button class="hero__button
            z-30 rounded px-20 py-1
            border-white border-2
            text-white text-xl
            max-h-11 self-center
            max-sm:w-full max-sm:text-base
            max-sm:px-10">
            Demo drive
            </button>
        </div>
    </section>
    <section class="model-3">
        <picture class="model-3__picture" data-alt="Red Model 3 driving down a lakeside road" data-iesrc="../assets/images/Homepage-Model-3-Desktop-NA.avif">
            <source srcset="../assets/images/Homepage-Model-3-Mobile-NA.avif" media="(max-width: 599px)">
            <source srcset="../assets/images/Homepage-Model-3-Desktop-NA.avif" media="(min-width: 600px)">
            <source srcset="../assets/images/Homepage-Model-3-Mobile-NA.avif" media="(min-width: 600px) and (orientation:portrait)">
            <img class="model-3__image" src="../assets/images/Homepage-Model-3-Desktop-NA.avif" srcset="../assets/images/Homepage-Model-3-Desktop-NA.avif" alt="Red Model 3 driving down a lakeside road">
        </picture>
        <div class="model-3__container">
            
        </div>
    </section>
</template>

<script setup lang="ts">

</script>

<style lang="scss">


[class*='__container'] {
    max-width: 1370px;
    margin: 0 auto;
    padding: 0 15px;
}


.hero__container {
    min-height: 100vh;
}





</style>