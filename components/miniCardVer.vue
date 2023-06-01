<template>
    <NuxtLink :to="to" class="mx-auto w-[188px]">
        <div class="w-[188px] h-[240px] overflow-hidden">
            <img class=" rounded-[4px] block hover:scale-110" :src="src" :alt="alt">
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