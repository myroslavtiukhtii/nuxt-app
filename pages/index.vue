<template>
    <div class="scroll__items">
        <section class="hero relative section">
            <div class="hero__container min-h-screen
                grid grid-cols-1
                grid-rows-2 justify-items-center">
                <div class="hero__titles opacity-80 pt-32 max-sm:pt-20 text-center">
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
                max-h-11 self-end mb-20
                max-sm:w-full max-sm:text-base
                max-sm:px-10">
                Demo drive
                </button>
            </div>
        </section>
        <section v-for="item in items" class="models relative section">
            <picture class="models__3__picture" data-alt="Red Model 3 driving down a lakeside road" data-iesrc="../assets/images/Homepage-Model-3-Desktop-NA.avif">
                <source srcset="../assets/images/Homepage-Model-3-Mobile-NA.avif" media="(max-width: 599px)">
                <source srcset="../assets/images/Homepage-Model-3-Desktop-NA.avif" media="(min-width: 600px)">
                <source srcset="../assets/images/Homepage-Model-3-Mobile-NA.avif" media="(min-width: 600px) and (orientation:portrait)">
                <img class="models__3__image
                absolute w-full h-full 
                object-cover top-0 
                left-0 -z-10" src="../assets/images/Homepage-Model-3-Desktop-NA.avif" srcset="../assets/images/Homepage-Model-3-Desktop-NA.avif" alt="Red Model 3 driving down a lakeside road">
            </picture>
            <div class="models__container min-h-screen
                grid grid-cols-1
                grid-rows-2 justify-items-center">
                <div class="models__titles pt-32 max-sm:pt-20 text-center">
                    <h2 class="model__title text-black text-5xl mb-5 max-sm:text-3xl"> {{ item.inventory }} </h2>
                    <h3 class="model__subtitle tracking-wide">
                       {{ item.subtitle }}
                    </h3>
                </div>
                <div class="models__buttons flex gap-5 flex-wrap justify-center self-end mb-20">
                    <button class="buttons__explore w-60 h-10 bg-white opacity-70 rounded-lg text-lg max-sm:w-full max-sm:text-base
                    max-sm:px-10 overflow-hidden">Explore Inventory</button>
                    <button class="buttons__custom w-60 h-10 bg-black opacity-70 rounded-lg text-white text-lg max-sm:w-full max-sm:text-base
                    max-sm:px-10 overflow-hidden">Custom Order</button>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup lang="ts">

const items = [
    {
        inventory: 'Model 3',
        subtitle: 'Starting at $32,740 After Federal Tax Credit',
    },
    {
        inventory: 'Model Y',
        subtitle: 'Starting at $40,240 After Federal Tax Credit',
    },
    {
        inventory: 'Model S',
        subtitle: 'Explore Inventory'
    },
    {
        inventory: 'Model X',
        subtitle: 'Explore Inventory'
    },
    {
        inventory: 'Solar Panels',
        subtitle: 'Schedule a Virtual Consultation'
    },
    {
        inventory: 'Solar Roof',
        subtitle: 'Produce Clean Energy From Your Roof'
    },
    {
        inventory: 'Powerwall',
        subtitle: ''
    },
    {
        inventory: 'Accessories',
        subtitle: ''
    },
];

</script>

<style lang="scss">

.scroll__items {
    scroll-snap-type: y mandatory;
    overflow-y: scroll;
    height: 100vh;
    scroll-behavior: smooth;
}

.section {
    scroll-snap-align: start;
    scroll-snap-stop: always;
}

[class*='__container'] {
    max-width: 1370px;
    margin: 0 auto;
    padding: 0 15px;
}










</style>