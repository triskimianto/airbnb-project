<template>
    <button class="bg-[#FF5A5F] h-[48px] w-[146px] rounded-[4px] text-[16px] text-white font-bold hover:bg-[#E55155]">{{ btnTitle }}</button>
</template>

<script setup>
    const props = defineProps({
        btnTitle: String,
    });
</script>