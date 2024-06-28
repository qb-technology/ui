<script setup lang='ts'>
defineProps({
    image: {
        type: String,
        default: '/phone_bg.png'
    }
})
</script>

<template>
    <div
        class="relative phone flex p-2 gap-2.5 ring ring-gray-300 dark:ring-gray-700 bg-gray-20 dark:bg-gray-800 box-border rounded-[60px] overflow-hidden">
        <NuxtImg :src="image" class="flex w-full rounded-[60px]" />
        <!--island-->
        <div class="absolute top-0 grid place-content-center w-full h-fit pt-7">
            <div class="island rounded-2xl bg-gray-300 dark:bg-gray-700"></div>
        </div>
    </div>
</template>

<style scoped>
.phone {
    aspect-ratio: 1/2;
    max-width: 366px;
}

.island {
    width: 105px;
    height: 30px;

}
</style>