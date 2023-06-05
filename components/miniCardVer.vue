<template>
    <NuxtLink :to="to" class="mx-auto w-[188px]">
        <div class="flex justify-center items-center w-[188px] h-[240px] overflow-hidden">
            <div class="img-container overflow-hidden hover:rounded-[4px] cursor-pointer">
                <img class="object-contain rounded-[4px]" :src="src" :alt="alt">
            </div>
        </div>
        <div class="my-2">
            <h1 class="text-[10px] text-start text-[#767676] font-bold uppercase">{{ country }}</h1>
            <h1 class="text-[16px] text-start text-[#484848] font-bold mt-1">{{ title }}</h1>
        </div>
        <h1 class="text-[14px] text-start text-[#484848] font-light">{{ desc }}</h1>        
        <div class="flex flex-row mt-[5px] items-center">
            <h1 class="text-[12px] text-start text-[#008489] font-bold">{{ rating }}</h1>
            <img class="w-[8px] h-[8px] ml-1" src="/icons/star-green.png" alt="star">
        </div>
    </NuxtLink>
</template>

<script setup>
    const props = defineProps({
        to: String,
        id: Number,
        src: String,
        alt: String,
        country: String,
        title: String,
        desc: String,
        rating: String,
    });
</script>

<style>
    .img-container {
        position: relative;
    }

    .img-container:hover::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.15); /* Ubah nilai alpha (0.5) sesuai keinginan Anda */
        z-index: 1;
    }

    .img-container:hover img {
        opacity: 0.9; /* Ubah nilai opasitas (0.7) sesuai keinginan Anda */        
    }
</style>