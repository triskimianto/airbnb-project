<template>
    <div class="w-full md:w-[391px]">
        <div class="relative overflow-hidden">
            <div class="absolute z-10 mt-[90px] ml-[160px] md:ml-[167px]">
                <img class="block w-[58px] h-[58px]" src="/icons/airbnb.png" alt="">
            </div>
            <img class="w-full md:w-[391px] h-[239px] rounded-[12px]" :src="src" :alt="alt">
            <div class="absolute inset-0 bg-black opacity-[15%] rounded-[12px]"></div>            
        </div>
        <h1 class="text-start text-[12px] text-[#914669] font-bold uppercase mt-2.5">{{ plus }}</h1>
        <h1 class="text-start text-[14px] text-[#484848] font-normal mt-2.5">{{ desc }}</h1>
    </div>
</template>

<script setup>
    const props = defineProps({
        src: String,
        alt: String,
        plus: String,
        desc: String,
    });
</script>