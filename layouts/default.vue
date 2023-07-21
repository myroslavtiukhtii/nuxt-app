<template>
    <header class="header z-30 p-5">
        <div class="header__container flex items-center justify-between">
            <NuxtLink to="/" aria-label="Tesla Logo" class="cursor-pointer z-30">
                <svg class="header__icon__svg w-36 max-sm:w-32" viewBox="0 0 342 35" xmlns="http://www.w3.org/2000/svg"><path d="M0 .1a9.7 9.7 0 0 0 7 7h11l.5.1v27.6h6.8V7.3L26 7h11a9.8 9.8 0 0 0 7-7H0zm238.6 0h-6.8v34.8H263a9.7 9.7 0 0 0 6-6.8h-30.3V0zm-52.3 6.8c3.6-1 6.6-3.8 7.4-6.9l-38.1.1v20.6h31.1v7.2h-24.4a13.6 13.6 0 0 0-8.7 7h39.9v-21h-31.2v-7h24zm116.2 28h6.7v-14h24.6v14h6.7v-21h-38zM85.3 7h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 13.8h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 14.1h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zM308.5 7h26a9.6 9.6 0 0 0 7-7h-40a9.6 9.6 0 0 0 7 7z"></path>
                </svg>
                <span class="visually_hidden">Tesla homepage</span>
            </NuxtLink>
            <ul :class="{ active: isActive }"  class="header__list flex text-white space-x-3 z-30">
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Model S</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Model 3</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Model X</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Model Y</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Solar Roof</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Solar Panels</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Powerwall</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Shop</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Account</NuxtLink>
                </li>
                <li class="header__list__item font-medium px-3 py-1 rounded">
                    <NuxtLink to="/about">Menu</NuxtLink>
                </li> 
            </ul>
            <button @click="openMenu()" class="header__menu text-white">Menu</button>
        </div>
    </header>
    <div class="main relative">
        <div class="main__container">
            <slot />
        </div>
    </div>
</template>

<script setup lang="ts">

import { ref } from 'vue';

const isActive = ref(false);

const openMenu = () => {
  isActive.value = !isActive.value; 
};


</script>

<style lang="scss" scoped>

.main__container {
    width: 100%;
    min-height: 100vh;
}

.header__list {
    @media (max-width: 1200px) {
        padding-top: 10%;
        flex-direction: column;
        color: #000;
        position: fixed;
        top: 0;
        right: -100%;
        background-color: #fff;
        z-index: 40;
        min-height: 100vh;
        width: 50%;

        .header__list__item {
            margin-left: 0;
        }

    }
}

.header__list.active {
    right: 0;
}

.header__list__item {
    position: relative;
    transition: .5s ease-in;
    overflow: hidden;

    &::before {
        content: '';
        width: 100%;
        min-height: 100%;
        position: absolute;
        top: 0;
        left: -150%;
        border-radius: inherit;
        backdrop-filter: blur(8px);
        background-color: rgba(255, 255, 255, 0.181);
        transition: .5s ease-in;
        z-index: -1;
    }

}
.header__list__item:hover {

    &::before {
        left: 0;
    }
}

.header__icon__svg {
    fill: #fff;
}

.header__menu {
    display: none;
    @media (max-width: 1200px) {
        border-radius: 5px;
        padding: 3px 7px;
        display: block;
        background-color: #b1b1b168;
        backdrop-filter: blur(25px);
    }
}

</style>