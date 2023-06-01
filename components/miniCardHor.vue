<template>
    <NuxtLink :to="to" class="flex flex-row items-center w-full md:w-[391px] bg-white border rounded-[12px] hover:shadow-lg">
        <img class="w-[121px] h-[85px] object-cover rounded-l-[12px] " :src="src" :alt="alt">
        <div class="px-10">
            <p class="text-medium text['#484848'] font-medium">
                {{ title }}
            </p>
        </div>
    </NuxtLink>
</template>

<script setup>
    const props = defineProps({
        to: String,
        src: String,
        alt: String,
        title: String,
    });
</script>