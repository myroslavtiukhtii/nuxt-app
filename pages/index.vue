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
                    src="/videos/Homepage-Demo-Drive-Desktop-NA.webm"
                    type="video/mp4"/> Your browser does not support the video tag.
                </video>
                <button class="hero__button
                z-10 rounded px-20 py-1
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
            <picture class="models__picture" :data-alt="item.alt" :data-iesrc=item.srcDesktop>
                <source :srcset="item.srcMobile" media="(max-width: 599px)">
                <source :srcset=item.srcDesktop media="(min-width: 600px)">
                <source :srcset=item.srcMobile media="(min-width: 600px) and (orientation:portrait)">
                <nuxt-img class="models__image
                absolute w-full h-full 
                object-cover top-0 
                left-0 -z-10" :src=item.srcDesktop :srcset=item.srcDesktop :alt=item.alt />
            </picture>
            <div class="models__container  min-h-screen
                grid grid-cols-1
                grid-rows-2 justify-items-center">
                <div class="models__titles pt-32 max-sm:pt-20 text-center">
                    <h2 class="models__title text-black text-5xl mb-5 max-sm:text-3xl"> {{ item.inventory }} </h2>
                    <h3 class="models__subtitle tracking-wide">
                       {{ item.subtitle1 }}
                    </h3>
                    <h4 class="models__subtitle tracking-wide">
                        {{ item.subtitle2 }}
                    </h4>
                </div>
                <div class="models__buttons flex gap-5 flex-wrap justify-center self-end mb-20">
                    <button class="buttons__explore w-60 h-10 bg-white opacity-70 rounded-lg text-lg max-sm:w-full max-sm:text-base
                    max-sm:px-10 overflow-hidden">{{ item.button1 }}</button>
                    <button v-show="item.button2" class="buttons__custom w-60 h-10 bg-black opacity-70 rounded-lg text-white text-lg max-sm:w-full max-sm:text-base
                    max-sm:px-10 overflow-hidden">{{ item.button2 }}</button>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup lang="ts">

import { onMounted, ref } from 'vue';

const items = [
    {
        inventory: 'Model 3',
        subtitle1: 'Starting at $32,740',
        subtitle2: 'After Federal Tax Credit',
        srcMobile: '/img/homepage/Homepage-Model-3-Mobile-NA.avif',
        srcDesktop: '/img/homepage/Homepage-Model-3-Desktop-NA.avif',
        alt: 'Model 3',
        button1: 'Explore Inventory',
        button2: 'Custom Order'
    },
    {
        inventory: 'Model Y',
        subtitle1: 'Starting at $40,240',
        subtitle2: ' After Federal Tax Credit',
        srcMobile: '/img/homepage/Homepage-ModelY-LHD-Mobile.avif',
        srcDesktop: '/img/homepage/Homepage-Model-Y-Global-Desktop.avif',
        alt: 'Model Y',
        button1: 'Explore Inventory',
        button2: 'Custom Order'
    },
    {
        inventory: 'Model S',
        subtitle1: 'Explore Inventory',
        srcMobile: '/img/homepage/Homepage-Model-S-Mobile-LHD-6.22.avif',
        srcDesktop: '/img/homepage/Homepage-Model-S-Desktop-LHD-6.22.avif',
        alt: 'Model S',
        button1: 'Explore Inventory',
        button2: 'Demo drive'
    },
    {
        inventory: 'Model X',
        subtitle1: 'Explore Inventory',
        srcMobile: '/img/homepage/Homepage-Model-X-Mobile-LHD_001.avif',
        srcDesktop: '/img/homepage/Homepage-Model-X-Desktop-LHD.avif',
        alt: 'Model X',
        button1: 'Explore Inventory',
        button2: 'Demo drive'
    },
    {
        inventory: 'Solar Panels',
        subtitle1: 'Schedule a Virtual Consultation',
        srcMobile: '/img/homepage/Homepage-SolarPanels-Mobile.avif',
        srcDesktop: '/img/homepage/425_HP_SolarPanels_D.avif',
        alt: 'Solar Panels',
        button1: 'Order Now',
        button2: 'Learn more'
    },
    {
        inventory: 'Solar Roof',
        subtitle1: 'Produce Clean Energy From Your Roof',
        srcMobile: '/img/homepage/Homepage-SolarRoof-Mobile.avif',
        srcDesktop: '/img/homepage/Homepage-SolarRoof-Desktop-Global.avif',
        alt: 'Solar Roof',
        button1: 'Order Now',
        button2: 'Learn more'
    },
    {
        inventory: 'Powerwall',
        subtitle1: '',
        srcMobile: '/img/homepage/Homepage-Powerwall-Mobile.avif',
        srcDesktop: '/img/homepage/Homepage-Powerwall-Desktop.avif',
        alt: 'Powerwall',
        button1: 'Order Now',
        button2: 'Learn more'
    },
    {
        inventory: 'Accessories',
        subtitle1: '',
        srcMobile: '/img/homepage/Homepage-Accessories-Mobile-NA-APAC.avif',
        srcDesktop: '/img/homepage/Homepage-Accessories-Desktop-NA-APAC.avif',
        alt: 'Accessories',
        button1: 'Shop Now',
        button2: ''
    },
];


onMounted(() => {

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('active');
        } else {
            entry.target.classList.remove('active');
        }
      });
    },
    {
      threshold: 0.5,
    }
  );

  document.querySelectorAll('.models__container').forEach((item) => {
    observer.observe(item);
  });
});



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

.models__container {
    opacity: 0.2;
    transform: translateY(2px);
    transition: .3s ease-in-out;
}

.models__container.active {
    opacity: 1;
    transform: translateY(0);
}














</style>