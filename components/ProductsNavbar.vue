<template>
    <nav class="w-full parallax fixed flex flex-row bg-white border-b border-gray-200 justify-between items-center py-4 z-10">
        <div class="flex justify-between items-center w-[388px] md:w-[1206px] mx-auto">
            <NuxtLink to="/">
                <img class="w-full h-full" :src="navBrandSrc" alt="nav-brand">
            </NuxtLink>
            <div class="hidden md:block w-[460.69px] h-[48px] border border-gray-200 rounded-full shadow p-[7px]">
                <div class="flex justify-between items-center">
                    <div class="pl-4">                        
                        <input type="text" v-model="searchQuery" class="w-[366px] text-[#767676] text-[14px] font-normal leading-[18px]" placeholder="Cari produk..." @input="handleSearchInput" />
                        <button v-show="searchQuery" class="absolute pl-1 top-1/2 transform -translate-y-1/2" @click="resetSearch">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="#C4C4C4" class="w-5 h-5">
                                <path d="M6.28 5.22a.75.75 0 00-1.06 1.06L8.94 10l-3.72 3.72a.75.75 0 101.06 1.06L10 11.06l3.72 3.72a.75.75 0 101.06-1.06L11.06 10l3.72-3.72a.75.75 0 00-1.06-1.06L10 8.94 6.28 5.22z" />
                            </svg>
                        </button>
                    </div>
                    <button class="bg-[#FF5A5F] rounded-full p-2" @click="openModal">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-4 h-4">
                            <path fill-rule="evenodd" d="M10.5 3.75a6.75 6.75 0 100 13.5 6.75 6.75 0 000-13.5zM2.25 10.5a8.25 8.25 0 1114.59 5.28l4.69 4.69a.75.75 0 11-1.06 1.06l-4.69-4.69A8.25 8.25 0 012.25 10.5z" clip-rule="evenodd" />
                        </svg>
                    </button>
                </div>                
            </div>
            <div class="md:w-[117px] h-[42px]">
                <div class="flex justify-between items-center gap-x-2">                
                    <button class="bg-white hover:bg-gray-100 rounded-full p-3">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="#484848" class="w-5 h-5">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 21a9.004 9.004 0 008.716-6.747M12 21a9.004 9.004 0 01-8.716-6.747M12 21c2.485 0 4.5-4.03 4.5-9S14.485 3 12 3m0 18c-2.485 0-4.5-4.03-4.5-9S9.515 3 12 3m0 0a8.997 8.997 0 017.843 4.582M12 3a8.997 8.997 0 00-7.843 4.582m15.686 0A11.953 11.953 0 0112 10.5c-2.998 0-5.74-1.1-7.843-2.918m15.686 0A8.959 8.959 0 0121 12c0 .778-.099 1.533-.284 2.253m0 0A17.919 17.919 0 0112 16.5c-3.162 0-6.133-.815-8.716-2.247m0 0A9.015 9.015 0 013 12c0-1.605.42-3.113 1.157-4.418" />
                        </svg>
                    </button>
                    <button class="bg-white border border-gray-200 rounded-full pl-3 pr-[5px] py-[5px]">
                        <div class="flex items-center gap-x-3">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-5 h-5">
                                <path fill-rule="evenodd" d="M3 6.75A.75.75 0 013.75 6h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 6.75zM3 12a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 12zm0 5.25a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75a.75.75 0 01-.75-.75z" clip-rule="evenodd" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#767676" class="w-8 h-8">
                                <path fill-rule="evenodd" d="M18.685 19.097A9.723 9.723 0 0021.75 12c0-5.385-4.365-9.75-9.75-9.75S2.25 6.615 2.25 12a9.723 9.723 0 003.065 7.097A9.716 9.716 0 0012 21.75a9.716 9.716 0 006.685-2.653zm-12.54-1.285A7.486 7.486 0 0112 15a7.486 7.486 0 015.855 2.812A8.224 8.224 0 0112 20.25a8.224 8.224 0 01-5.855-2.438zM15.75 9a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z" clip-rule="evenodd" />
                            </svg>
                        </div>
                    </button>
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
    const navBrandSrc = ref('/icons/airbnb-nav-red-text.png');

    const showModal = ref(false);
    const searchQuery = ref('');
    const searchResults = ref([]);

    const searchProducts = async () => {
        const url = `https://dummyjson.com/products/search?q=${encodeURIComponent(searchQuery.value)}`;
        const response = await fetch(url);
        const data = await response.json();
        searchResults.value = data.products;
    };

    const openModal = () => {
        showModal.value = true;
    }

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

    watch(searchQuery, () => {
        if (searchQuery.value.length > 2) {
            searchProducts()            
        } else {
            searchResults.value = []
        }
    })
</script>