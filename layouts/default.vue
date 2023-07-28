<template>
    <header class="header fixed top-0 left-0 z-30 p-5">
        <div class="header__container flex items-center justify-between">
            <NuxtLink to="/" aria-label="Tesla Logo" class="cursor-pointer z-30">
                <svg class="header__icon w-36 max-sm:w-32" viewBox="0 0 342 35" xmlns="http://www.w3.org/2000/svg"><path d="M0 .1a9.7 9.7 0 0 0 7 7h11l.5.1v27.6h6.8V7.3L26 7h11a9.8 9.8 0 0 0 7-7H0zm238.6 0h-6.8v34.8H263a9.7 9.7 0 0 0 6-6.8h-30.3V0zm-52.3 6.8c3.6-1 6.6-3.8 7.4-6.9l-38.1.1v20.6h31.1v7.2h-24.4a13.6 13.6 0 0 0-8.7 7h39.9v-21h-31.2v-7h24zm116.2 28h6.7v-14h24.6v14h6.7v-21h-38zM85.3 7h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 13.8h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 14.1h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zM308.5 7h26a9.6 9.6 0 0 0 7-7h-40a9.6 9.6 0 0 0 7 7z"></path>
                </svg>
                <span class="visually_hidden">Tesla homepage</span>
            </NuxtLink>
            <ul :class="{ active: isActive }"  class="header__list flex space-x-3 z-30">
                <li @click="openMenu" class="header__list__close">
                    <Icon name="ep:close" />
                </li>
                <li v-for="item in menuLinks" @click="closeMenu" class="header__list__item text-white font-medium px-3 py-1 rounded">
                    <NuxtLink :to=item.link> {{ item.title }} </NuxtLink>
                </li>
            </ul>
            <ul class="header__icons flex space-x-3 z-30">
                <li @click="openMenu" class="header__icons__item">
                    <Icon class="header__icon text-white w-5 h-5" name="quill:cog" />
                </li>
                <li @click="openMenu" class="header__icons__item">
                    <Icon class="header__icon text-white w-5" name="streamline:programming-web-server-world-internet-earth-www-globe-worldwide-web-network" />
                </li>
                <li @click="openMenu" class="header__icons__item">
                    <Icon class="header__icon text-white w-5" name="fa:user" />
                </li>
            </ul>
            <button @click="openMenu" class="header__menu text-white z-30">Menu</button>
        </div>
    </header>
    <main @click="closeMenu" class="main">
        <slot />
    </main>
</template>

<script setup lang="ts">

import { onMounted, ref } from 'vue';

const menuLinks = [
    {
        title: 'Vehicles',
        link: '/',
    },
    {
        title: 'Energy',
        link: '/',
    },
    {
        title: 'Charging',
        link: '/',
    },
    {
        title: 'Discover',
        link: '/',
    },
    {
        title: 'Shop',
        link: '/',
    }
];

const isActive = ref(false);

const openMenu = () => {
  isActive.value = !isActive.value;
};

const closeMenu = () => {
    isActive.value = false
};



</script>

<style lang="scss" scoped>

.header {
    width: 100%;
}

.header__list__close {
    @media (min-width: 1201px) {
        display: none;
    }
}

.header__list {
    transition: .5s ease-in;


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
        opacity: 0;

        .header__list__item {
            margin-left: 0;
            color: #000;
        }

        .header__list__close {
            position: absolute;
            top: 15px;
            right: 15px;
        }
    }
}

.header__list.active {
    opacity: 1;
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

.header__icon {
    fill: #fff;
}


.header__icons {
    @media (max-width: 1200px) {
        display: none;
    }
}

</style>