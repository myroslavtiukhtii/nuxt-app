<template>
    <header class="header mb-10">
        <div class="header__container bg-amber-200 rounded-md shadow-lg">
            <ul class="header__list flex p-5">
                <li class="header__list__item mr-10 font-medium">
                    <NuxtLink to="/">HOME</NuxtLink>
                </li>
                <li class="header__list__item font-medium">
                    <NuxtLink to="/about">ABOUT</NuxtLink>
                </li>
            </ul>
        </div>
    </header>
    <div class="main">
        <div class="main__container">
            <slot />
        </div>
    </div>
</template>

<script setup lang="ts">

</script>

<style scoped>

</style>