<script setup lang='ts'>

const icons = [
    {
        name: 'mdi:youtube',
        to: '#'
    },
    {
        name: 'uil:facebook-f',
        to: '#'
    },
    {
        name: 'ri:twitter-x-line',
        to: '#'
    },
    {
        name: 'mdi:instagram',
        to: '#'
    },
    {
        name: 'ri:linkedin-fill',
        to: '#'
    },
]
</script>

<template>
    <div class="space-y-6 md:space-y-12 pt-12 md:pt-16 lg:pt-24">
        <div class="flex flex-col md:flex-row items-center justify-between gap-6">
            <LogoV1 />
            <UHorizontalNavigation :links="menuLinks"
                :ui="{ wrapper: 'w-fit', container: 'flex-wrap justify-center md:justify-start md:flex-nowrap' }" />
        </div>

        <UDivider />

        <div
            class="flex flex-col md:flex-row items-center justify-between gap-5 md:gap-1 pb-4 md:pb-5 text-gray-700 dark:text-gray-200">
            <p>QB TECH &copy; 2024. All rights reserved</p>
            <div class="flex items-center gap-2">
                <UButton v-for="link in icons" variant="ghost" color="gray" :to="link.to" :icon="link.name" />
            </div>
        </div>
    </div>
</template>