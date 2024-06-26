<script setup lang='ts'>

// const links = [
//     {
//         label: 'Home',
//         to: '/',

//     },
//     {
//         label: 'Projects',
//         to: '/projects',
//         badge: 100

//     },
//     {
//         label: 'Services',
//         to: '/services',

//     },
//     {
//         label: 'Pricing',
//         to: '/pricing',

//     },
//     {
//         label: 'Contact',
//         to: '/contact',

//     },
// ]

defineEmits(['getStarted'])
</script>

<template>
    <header class="flex items-center justify-between gap-6">
        <LogoV1 class="flex-grow" />

        <UHorizontalNavigation :links="menuLinks" :ui="{ wrapper: 'w-fit hidden md:block' }" />

        <div class="flex-grow justify-end gap-5 hidden md:flex">
            <DarkMode />
            <UButton label="Get Started" @click="$emit('getStarted')" />
        </div>

        <TemplateHeaderMobile class="md:hidden" />

    </header>
</template>