<template>
    <section class="hero pt-32 relative">
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
    <section class="models relative pt-32 pb-32">
        <picture class="models__3__picture" data-alt="Red Model 3 driving down a lakeside road" data-iesrc="../assets/images/Homepage-Model-3-Desktop-NA.avif">
            <source srcset="../assets/images/Homepage-Model-3-Mobile-NA.avif" media="(max-width: 599px)">
            <source srcset="../assets/images/Homepage-Model-3-Desktop-NA.avif" media="(min-width: 600px)">
            <source srcset="../assets/images/Homepage-Model-3-Mobile-NA.avif" media="(min-width: 600px) and (orientation:portrait)">
            <img class="models__3__image
            absolute w-full h-full 
            object-cover top-0 
            left-0 -z-10" src="../assets/images/Homepage-Model-3-Desktop-NA.avif" srcset="../assets/images/Homepage-Model-3-Desktop-NA.avif" alt="Red Model 3 driving down a lakeside road">
        </picture>
        <div class="models__container
            grid grid-cols-1
            grid-rows-2 justify-items-center">
            <div class="models__titles">
                <h2 class="model__title text-black text-5xl mb-5">Model 3</h2>
                <h3 class="model__subtitle tracking-wide">Starting at 
                    <span class="model__price">$32,740</span>
                </h3>
                <span class="model__subtitle tracking-wide">After Federal Tax Credit</span>
            </div>
            <div class="models__buttons flex gap-5 flex-wrap justify-center self-center">
                <button class="buttons__explore w-60 h-10 bg-white opacity-70 rounded-lg text-lg">Explore Inventory</button>
                <button class="buttons__custom w-60 h-10 bg-black opacity-70 rounded-lg text-white text-lg
                ">Custom Order</button>
            </div>
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

.hero__container, .models__container {
    min-height: 100vh;
}

.models {

    &__titles {
        text-align: center;
    }

}








</style>