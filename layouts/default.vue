<template>
    <header :class="{ active: isActive }" class="header fixed top-0 left-0 z-30 p-5">
        <div class="header__container flex items-center justify-between">
            <NuxtLink to="/" aria-label="Tesla Logo" class="cursor-pointer z-50">
                <svg class="header__icon w-36 max-sm:w-32" viewBox="0 0 342 35" xmlns="http://www.w3.org/2000/svg"><path d="M0 .1a9.7 9.7 0 0 0 7 7h11l.5.1v27.6h6.8V7.3L26 7h11a9.8 9.8 0 0 0 7-7H0zm238.6 0h-6.8v34.8H263a9.7 9.7 0 0 0 6-6.8h-30.3V0zm-52.3 6.8c3.6-1 6.6-3.8 7.4-6.9l-38.1.1v20.6h31.1v7.2h-24.4a13.6 13.6 0 0 0-8.7 7h39.9v-21h-31.2v-7h24zm116.2 28h6.7v-14h24.6v14h6.7v-21h-38zM85.3 7h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 13.8h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 14.1h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zM308.5 7h26a9.6 9.6 0 0 0 7-7h-40a9.6 9.6 0 0 0 7 7z"></path>
                </svg>
                <span class="visually_hidden">Tesla homepage</span>
            </NuxtLink>
            <ul class="header__list flex space-x-3 z-40">
                <li @click="closeMenu" class="header__list__close">
                    <Icon class="w-5 h-5" name="ep:close" />
                </li>
                <li 
                @click="openMenuLink(index)"
                :class="{ active: activeIndex === index }"
                v-for="item, index, in menuLinks"
                class="header__list__item text-black font-medium px-3 py-1 rounded">
                    <NuxtLink class="list__item__title">
                        {{ item.title }} 
                        <Icon class="item__title__icon w-5 h-5" name="ep:arrow-right" />
                    </NuxtLink>
                    <div class="hover__block__menu">
                        <ul v-show="item.subItems.length > 0" class="header__hover__menu">
                            <li v-for="subItem in item.subItems" class="hover__menu__item">
                                <img class="menu__item__img" :src=subItem.img>
                                <div class="menu__item__block">
                                    <h3 class="menu__item__title mb-2">{{ subItem.title }}</h3>
                                    <div class="menu__item__links text-sm text-zinc-600">
                                        <NuxtLink>{{ subItem.subtitle1 }}</NuxtLink>
                                        <NuxtLink>{{ subItem.subtitle2  }}</NuxtLink>
                                    </div>
                                </div>
                            </li>
                        </ul>
                        <ul v-show="item.links?.length" class="header__hover__links">
                            <ul class="hover__links__list">
                                <NuxtLink class="text-sm" v-for="links in item.links" :to=links.path>{{ links.title }}</NuxtLink> 
                            </ul>
                            <ul class="hover__links__list">
                                <NuxtLink class="text-sm"  v-for="links in item.links2" :to=links.path>{{ links.title }}</NuxtLink> 
                            </ul>
                            <ul class="hover__links__list"> 
                                <NuxtLink class="text-sm"  v-for="links in item.links3" :to=links.path>{{ links.title }}</NuxtLink> 
                            </ul>
                        </ul>
                    </div>
                </li>
            </ul>
            <ul class="header__icons flex space-x-3 z-40">
                <NuxtLink to="/" class="header__icons__item">
                    <Icon class="header__icon text-white w-5 h-5" name="quill:cog" />
                </NuxtLink>
                <NuxtLink to="/" class="header__icons__item">
                    <Icon class="header__icon text-white w-5" name="streamline:programming-web-server-world-internet-earth-www-globe-worldwide-web-network" />
                </NuxtLink>
                <NuxtLink to="/" class="header__icons__item">
                    <Icon class="header__icon text-white w-5" name="fa:user" />
                </NuxtLink>
            </ul>
            <button @click="openMenu" class="header__menu text-white z-40">Menu</button>
        </div>
    </header>
    <main @click="closeMenu" class="main">
        <slot />
    </main>
</template>

<script setup lang="ts">

import { ref } from 'vue';

const menuLinks = [
    {
        title: 'Vehicles',
        subItems: [
            {
                title: 'Model S',
                img: 'img/header/vehicles/Mega-Menu-Vehicles-Model-S.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            },
            {
                title: 'Model 3',
                img: 'img/header/vehicles/Mega-Menu-Vehicles-Model-3.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            },
            {
                title: 'Model X',
                img: 'img/header/vehicles/Mega-Menu-Vehicles-Model-X.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            },
            {
                title: 'Model Y',
                img: 'img/header/vehicles/Mega-Menu-Vehicles-Model-Y.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            }
        ],
        links: [
            {
                title: 'Inventory',
                path: '/'
            },
            {
                title: 'Used Cars',
                path: '/'
            },
            {
                title: 'Cybertruck',
                path: '/'
            },
            {
                title: 'Semi',
                path: '/'
            },
            {
                title: 'Roadster',
                path: '/'
            },
            {
                title: 'Compare',
                path: '/'
            },
            {
                title: 'Fleet',
                path: '/'
            },
            {
                title: 'Demo Drive',
                path: '/'
            },
            {
                title: 'Trade-in',
                path: '/'
            }
        ], 
    },
    {
        title: 'Energy',
        subItems: [
            {
                title: 'Solar Panels',
                img: 'img/header/energy/Mega-Menu-Energy-Solar-Panels.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            },
            {
                title: 'Solar Roof',
                img: 'img/header/energy/Mega-Menu-Energy-Solar-Roof.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            },
            {
                title: 'Powerwall',
                img: 'img/header/energy/Mega-Menu-Energy-Powerwall-US.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            },
            {
                title: 'Megapack',
                img: 'img/header/energy/Mega-Menu-Energy-Megapack.avif',
                subtitle1: 'Learn',
                subtitle2: 'Order',
            }
        ],
        links: [
            {
                title: 'Utilities',
                path: '/'
            },
            {
                title: 'Commercial',
                path: '/'
            },
            {
                title: 'Schedule a Consultation',
                path: '/'
            },
        ], 
    },
    {
        title: 'Charging',
        subItems: [
            {
                title: 'Charging',
                img: 'img/header/charging/Mega-Menu-Charging-Charging.avif',
                subtitle1: 'Learn',
                subtitle2: '',
            },
            {
                title: 'Home Charging',
                img: 'img/header/charging/Mega-Menu-Charging-Home-Charging.avif',
                subtitle1: 'Learn',
                subtitle2: 'Shop',
            },
            {
                title: 'Supercharging',
                img: 'img/header/charging/Mega-Menu-Charging-Supercharging.avif',
                subtitle1: 'Learn',
                subtitle2: 'Find',
            },
        ],
        links: [
            {
                title: 'Charging Calculator',
                path: '/'
            },
            {
                title: 'Trip Planner',
                path: '/'
            },
            {
                title: 'Supercharger Voting',
                path: '/'
            },
            {
                title: 'Destination Charging',
                path: '/'
            },
            {
                title: 'Commercial Charging',
                path: '/'
            },
            {
                title: 'Become a Site Host',
                path: '/'
            },
        ], 
    },
    {
        title: 'Discover',
        subItems: [],
        links: [
            {
                title: 'Demo Drive',
                path: '/'
            },
            {
                title: 'Insurance',
                path: '/'
            },
            {
                title: 'Video Guides',
                path: '/'
            },
            {
                title: 'Customer Stories',
                path: '/'
            },
            {
                title: 'Events',
                path: '/'
            },
        ], 
        links2: [
            {
                title: 'Find Us',
                path: '/'
            },
            {
                title: 'Trip Planner',
                path: '/'
            },
            {
                title: 'Find a Collision Center',
                path: '/'
            },
            {
                title: 'Find a Certified Installer',
                path: '/'
            },
        ], 
        links3: [
            {
                title: 'About',
                path: '/'
            },
            {
                title: 'Careers',
                path: '/'
            },
            {
                title: 'Investor Relations',
                path: '/'
            },
        ],
    },
    {
        title: 'Shop',
        subItems: [
            {
                title: 'Charging',
                img: 'img/header/shop/Mega-Menu-Shop-Charging.avif',
                subtitle1: '',
                subtitle2: '',
            },
            {
                title: 'Vehicle Accessories',
                img: 'img/header/shop/Mega-Menu-Shop-Vehicle-Accessories.avif',
                subtitle1: '',
                subtitle2: '',
            },
            {
                title: 'Apparel',
                img: 'img/header/shop/Mega-Menu-Shop-Apparel.avif',
                subtitle1: '',
                subtitle2: '',
            },
            {
                title: 'Lifestyle',
                img: 'img/header/shop/Mega-Menu-Shop-Lifestyle.avif',
                subtitle1: '',
                subtitle2: '',
            },
        ],
    },
];

const isActive = ref(false);
const activeIndex = ref(-1);

const openMenu = () => {
  isActive.value = !isActive.value;
};

const closeMenu = () => {
    isActive.value = false;
    const activeItems = document.querySelectorAll('.header__list__item');
    activeItems.forEach((item) => {
        item.classList.remove('active');
    })
};

const openMenuLink = (index: number) => {
    if (activeIndex.value === index) {
      activeIndex.value = -1; 
    } else {
      activeIndex.value = index; 
    }
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
        padding-top: 55px;
        flex-direction: column;
        gap: 25px;
        position: fixed;
        top: -1%;
        right: 0;
        background-color: #fff;
        width: 100%;
        opacity: 0;
        visibility: hidden;
        z-index: 50;

        .header__list__item {
            margin-left: 0;
        }

        .header__list__close {
            position: absolute;
            top: 15px;
            right: 15px;
            z-index: 50;
        }
    }
}
.header__list__item {
    position: relative;
    transition: .5s ease-in;
    cursor: pointer;

    .list__item__title {
        display: flex;
        align-items: center;
        justify-content: space-between;
        mix-blend-mode: difference;
        color: #fff;
        font-weight: 400;
        transition: .5s ease-in;

        .item__title__icon {
            display: none;
            transition: .3s ease-in;
        }
        
        @media (max-width: 1200px) {
            font-size: 20px;
            color: #d2d2d2;
            margin-bottom: 15px;

            .item__title__icon {
                display: block;
            }
        }
    }
}
.header__list__item:hover  {
    @media (any-hover: hover) {
        background-color: #f3f3f385;

        .hover__block__menu {
            top: 0;
            opacity: 1;
            visibility: visible;
        }
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
.hover__block__menu {
    position: fixed;
    top: -1%;
    left: 0;
    width: 100%;
    background-color: #fff;
    padding: 90px;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    gap: 15px;
    transition: .5s ease-in;
    opacity: 0;
    visibility: hidden;
    z-index: -1;

    @media (max-width: 1200px) {
        position: relative;
        top: 0;
        padding: 5px;
        flex-wrap: wrap;
        justify-content: flex-start;
        opacity: 0;
        display: none;
    }
}
.header__hover__menu {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    justify-content: space-around;
    margin-bottom: 45px;

    .hover__menu__item {
        padding: 5px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .menu__item__block {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .menu__item__img {
        width: 100%;
        max-width: 230px;
        height: auto;
    }

    .menu__item__links {
        display: flex;
        align-items: center;
        gap: 15px;
        text-decoration: underline;
    }
}
.header__hover__links {
    display: flex;
    justify-items: center;
    gap: 35px;
    border-left: 1px solid #f3f3f3;
    padding-left: 15px;

    .hover__links__list {
        display: flex;
        flex-direction: column;
        gap: 5px;
    }

    @media (max-width: 1200px) {
        .hover__links__list {
            gap: 15px;
        }
    }
}
.header__icon {
    fill: #fff;
    transition: .5s ease-in;
    fill: #ffffff;
    color: #ffffff;
}
.header__icons {
    @media (max-width: 1200px) {
        display: none;
    }
}


///

.header.active {

    .header__list {
        opacity: 1;
        top: 0;
        visibility: visible;
        height: 100vh;
        overflow: scroll;
    }

    .header__list__item.active {
        z-index: 50;

        .hover__block__menu {
            opacity: 1;
            display: block;
            visibility: visible;
        }

        .item__title__icon {
            transform: rotate(90deg);
        }

    }

}

</style>