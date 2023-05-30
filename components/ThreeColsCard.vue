<template>
    <NuxtLink :to="to" class="w-full md:w-[289px]">
        <div class="w-[289px] h-[200px] overflow-hidden">
            <img class="w-full rounded-[4px] hover:scale-110" :src="src" :alt="alt">
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