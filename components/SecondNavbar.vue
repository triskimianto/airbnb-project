<template>
    <nav class="parallax flex flex-row justify-between items-center w-full px-6 py-4 bg-white text-[#484848] shadow">
        <NuxtLink to="/">
            <img class="w-[28.65px] h-[30.73px]" :src="navbarsrc" alt="nav-brand">
        </NuxtLink>
        <div class="hidden md:flex item-center space-x-6">
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">Indonesia (ID)</NuxtLink>
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">IDR</NuxtLink>
            <!-- <NuxtLink to="/" class="hover:text-[#FF5A5F]">Menjadi tuan rumah</NuxtLink> -->
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">Produk</NuxtLink>
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">Bantuan</NuxtLink>
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">Registrasi</NuxtLink>
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">Hubungkan</NuxtLink>
        </div>
        <div class="md:hidden">
            <button @click="toggleMobileMenu" class="block focus:outline-none">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                </svg>
            </button>
            <div v-if="isMobileMenuOpen" class="absolute mt-[18px] left-0 w-full bg-white text-[#484848] border-t shadow">
                <div class="flex flex-col space-y-4 p-4">
                    <NuxtLink to="/">Indonesia (ID)</NuxtLink>
                    <NuxtLink to="/">IDR</NuxtLink>
                    <!-- <NuxtLink to="/">Menjadi Tuan Rumah</NuxtLink> -->
                    <NuxtLink to="/">Produk</NuxtLink>
                    <NuxtLink to="/">Bantuan</NuxtLink>
                    <NuxtLink to="/">Registrasi</NuxtLink>
                    <NuxtLink to="/">Hubungkan</NuxtLink>
                </div>
            </div>
        </div>                        
    </nav>
</template>

<script setup>
    import { ref } from 'vue';
    import navbarsrc from "/icons/airbnb-nav-red.png";

    const isMobileMenuOpen = ref(false);

    const toggleMobileMenu = () => {
        isMobileMenuOpen.value = !isMobileMenuOpen.value;
    };
</script>