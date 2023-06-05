<template>
    <NuxtLink :to="to" class="mx-auto w-[289px]">
        <div class="flex justify-center items-center w-[289px] h-[200px] overflow-hidden">
            <div class="img-container overflow-hidden hover:rounded-[4px] cursor-pointer">
                <img class="object-contain rounded-[4px]" :src="src" :alt="alt">
            </div>
        </div>        
        <div class="flex flex-row justify-between items-center mt-2">
            <div class="flex flex-row items-center gap-3">
                <TagMini />
                <h1 class="text-[12px] text-[#767676] font-normal">{{ city }}</h1>
            </div>
            <div class="flex flex-row items-center gap-1">
                <img class="w-[8px] h-[8px]" src="/icons/star-red.png" alt="star">
                <h1 class="text-[12px] text-[#484848] font-medium">{{ rating }}</h1>
            </div>            
        </div>
        <h1 class="text-start text-[14px] text-[#484848] font-normal mt-2">{{ desc }}</h1>
    </NuxtLink>
    
</template>

<script setup>
    const props = defineProps({
        to: String,
        src: String,
        alt: String,
        city: String,
        rating: String,
        desc: String,
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