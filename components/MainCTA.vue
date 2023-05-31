<template>
    <NuxtLink :to="to">
        <button class="bg-[#FF5A5F] h-[48px] w-full rounded-[4px] text-[16px] text-white font-bold hover:bg-[#E55155]">{{ btnTitle }}</button>
    </NuxtLink>
</template>

<script setup>
    const props = defineProps({
        to: String,
        btnTitle: String,
    });
</script>