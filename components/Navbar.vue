<template>
    <nav class="parallax fixed flex flex-row justify-between items-center w-full px-6 py-4 z-20 text-white">
        <NuxtLink to="/">
            <img class="w-[28.65px] h-[30.73px]" :src="navBrandSrc" alt="nav-brand">
        </NuxtLink>
        <div class="hidden md:flex item-center space-x-6">
            <NuxtLink class="hover:text-[#FF5A5F] cursor-pointer" @click="showModal = true">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" :fill="searchBtnColor" class="w-6 h-6">
                    <path fill-rule="evenodd" d="M10.5 3.75a6.75 6.75 0 100 13.5 6.75 6.75 0 000-13.5zM2.25 10.5a8.25 8.25 0 1114.59 5.28l4.69 4.69a.75.75 0 11-1.06 1.06l-4.69-4.69A8.25 8.25 0 012.25 10.5z" clip-rule="evenodd" />
                </svg>
            </NuxtLink>
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">Indonesia (ID)</NuxtLink>
            <NuxtLink to="/" class="hover:text-[#FF5A5F]">IDR</NuxtLink>
            <!-- <NuxtLink to="/" class="hover:text-[#FF5A5F]">Menjadi tuan rumah</NuxtLink> -->            
            <NuxtLink to="/products" class="hover:text-[#FF5A5F]">Produk</NuxtLink>
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
                    <NuxtLink class="hover:text-[#FF5A5F] cursor-pointer" @click="showModal = true">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-6 h-6">
                            <path fill-rule="evenodd" d="M10.5 3.75a6.75 6.75 0 100 13.5 6.75 6.75 0 000-13.5zM2.25 10.5a8.25 8.25 0 1114.59 5.28l4.69 4.69a.75.75 0 11-1.06 1.06l-4.69-4.69A8.25 8.25 0 012.25 10.5z" clip-rule="evenodd" />
                        </svg>
                    </NuxtLink>
                    <NuxtLink to="/">Indonesia (ID)</NuxtLink>
                    <NuxtLink to="/">IDR</NuxtLink>
                    <!-- <NuxtLink to="/">Menjadi Tuan Rumah</NuxtLink> -->
                    <NuxtLink to="/products">Produk</NuxtLink>
                    <NuxtLink to="/">Bantuan</NuxtLink>
                    <NuxtLink to="/">Registrasi</NuxtLink>
                    <NuxtLink to="/">Hubungkan</NuxtLink>
                </div>
            </div>
        </div>                        
    </nav>
    <div v-if="showModal" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50 z-50">
        <div class="bg-white w-[388px] rounded-[12px] p-6">
            <div class="flex w-full justify-between items-center">
                <h1 class="text-[#484848] text-[22px] font-medium leading-[26px] pl-1.5 pt-1">Cari Produk</h1>                
                <button class="bg-white hover:bg-gray-200 rounded-full p-1.5" @click="closeModal">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-5 h-5">
                        <path fill-rule="evenodd" d="M5.47 5.47a.75.75 0 011.06 0L12 10.94l5.47-5.47a.75.75 0 111.06 1.06L13.06 12l5.47 5.47a.75.75 0 11-1.06 1.06L12 13.06l-5.47 5.47a.75.75 0 01-1.06-1.06L10.94 12 5.47 6.53a.75.75 0 010-1.06z" clip-rule="evenodd" />
                    </svg>
                </button>
            </div>
            <div class="mt-6 px-1.5">
                <hr class="h-px bg-gray-200 border-0 mb-6">
                <div class="flex justify-between border border-gray-200 rounded-[4px] overflow-hidden">
                    <div class="relative w-full">
                        <input type="text" v-model="searchQuery" class="w-full text-[#484848] text-[14px] font-normal leading-[18px] px-3 py-2" placeholder="Cari produk..." @input="handleSearchInput" />
                        <button v-if="searchResults.length > 0" class="absolute right-3 top-1/2 transform -translate-y-1/2" @click="resetSearch">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="#C4C4C4" class="w-5 h-5">
                                <path d="M6.28 5.22a.75.75 0 00-1.06 1.06L8.94 10l-3.72 3.72a.75.75 0 101.06 1.06L10 11.06l3.72 3.72a.75.75 0 101.06-1.06L11.06 10l3.72-3.72a.75.75 0 00-1.06-1.06L10 8.94 6.28 5.22z" />
                            </svg>
                        </button>
                    </div>
                    <button class="justify-end bg-[#FF5A5F] hover:bg-[#E55155] px-3 py-2" @click="searchProducts">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-5 h-5">
                            <path fill-rule="evenodd" d="M10.5 3.75a6.75 6.75 0 100 13.5 6.75 6.75 0 000-13.5zM2.25 10.5a8.25 8.25 0 1114.59 5.28l4.69 4.69a.75.75 0 11-1.06 1.06l-4.69-4.69A8.25 8.25 0 012.25 10.5z" clip-rule="evenodd" />
                        </svg>
                    </button>       
                </div>                         
            </div>
            <div v-if="searchResults.length > 0" class="mt-6 px-1.5">
                <hr class="h-px bg-gray-200 border-0 mb-6">   
                <div class="max-h-[200px] overflow-y-auto">
                    <NuxtLink :to="`/products/${s.id}`" v-for="s in searchResults" :key="s.id" class="flex w-full justify-between items-center py-1">
                        <h1 class="w-[350px] text-[#484848] text-[16px] font-medium leading-5">{{ s.title }}</h1>
                        <div class="w-[120px] h-[60px] border border-gray-200 rounded-[4px] overflow-hidden flex justify-center items-center mr-2">
                            <img class="object-contain" :src="s.thumbnail" :alt="s.title">
                        </div>
                    </NuxtLink>             
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import {ref, onMounted, onBeforeUnmount} from 'vue';    

    const showModal = ref(false);
    const searchQuery = ref('');
    const searchResults = ref([]);

    const searchProducts = async () => {
        const url = `https://dummyjson.com/products/search?q=${encodeURIComponent(searchQuery.value)}`;
        const response = await fetch(url);
        const data = await response.json();
        searchResults.value = data.products;
    };

    const closeModal = () => {
        showModal.value = false;
        searchResults.value = [];
    };

    const handleSearchInput = () => {
        searchResults = [];
    };

    const resetSearch = () => {
        searchQuery.value = '';
        searchResults.value = [];
    }

    const nav = ref(null);
    const navBrandSrc = ref('/icons/airbnb-nav.png');
    const searchBtnColor = ref('#FFFFFF');
    const isMobileMenuOpen = ref(false);

    const onScroll = () => {
        if (document.documentElement.scrollTop > 60 || document.body.scrollTop > 60) {
            nav.value.classList.add('bg-white', 'items-center', 'shadow');
            nav.value.classList.remove('text-white');
            navBrandSrc.value = '/icons/airbnb-nav-red.png';
            searchBtnColor.value = '#000000';
        } else {
            nav.value.classList.remove('bg-white', 'items-center', 'shadow');
            nav.value.classList.add('text-white');
            navBrandSrc.value = '/icons/airbnb-nav.png';
            searchBtnColor.value = '#FFFFFF';
        }
    };

    const toggleMobileMenu = () => {
        isMobileMenuOpen.value = !isMobileMenuOpen.value;
    };

    onMounted(() => {
        nav.value = document.querySelector('nav');
        window.addEventListener('scroll', onScroll);
    });

    onBeforeUnmount(() => {
        window.removeEventListener('scroll', onScroll);
    });
</script>