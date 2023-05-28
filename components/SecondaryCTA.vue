<template>
    <button class="flex flex-row items-center bg-white rounded-[4px] px-6 py-4">
        <span class="text-[10px] text-[#484848] font-bold uppercase">{{ btnTitle }}</span>
        <img class="w-[4px] h-[8px] ml-5" src="/icons/arrow-black.png" alt="arrow">
    </button>
</template>

<script setup>
    const props = defineProps({
        btnTitle: String,
    });
</script>