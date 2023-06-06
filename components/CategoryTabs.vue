<template>
    <div class="parallax fixed w-full bg-white mt-4 z-10 shadow">
        <div class="w-[388px] md:w-[1206px] mx-auto">
            <div class="relative max-md:sticky top-0 flex max-md:flex-col justify-around pt-2 max-md:pb-2 px-10 gap-x-2.5 transition-all ease category-tabs">
                <div class="relative w-full md:w-4/5 overflow-x-auto grid grid-flow-col auto-cols-max gap-x-6 z-10 scroll-smooth category-scroll pt-2 pl-6">                    
                    <NuxtLink v-for="(category, index) in categories" :key="index" :to="`#${category}`">
                        <div class="relative flex flex-col items-center gap-y-2.5 pb-3 opacity-70 hover:opacity-100 border-white hover:border-b-2 border-b-2 hover:border-gray-200 transition-all ease category-item">
                            <img src="https://a0.muscache.com/pictures/7630c83f-96a8-4232-9a10-0398661e2e6f.jpg" alt="" class="w-6 h-6" />
                            <h1 class="text-[#484848] text-[12px] font-medium leading-4">{{ category }}</h1>
                        </div>                
                    </NuxtLink>
                </div>
                <button class="relative hidden md:flex w-auto h-12 border rounded-[12px] justify-between items-center gap-x-2 max-md:z-10 px-3 mt-2">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-[14px] h-[14px]">
                        <path d="M18.75 12.75h1.5a.75.75 0 000-1.5h-1.5a.75.75 0 000 1.5zM12 6a.75.75 0 01.75-.75h7.5a.75.75 0 010 1.5h-7.5A.75.75 0 0112 6zM12 18a.75.75 0 01.75-.75h7.5a.75.75 0 010 1.5h-7.5A.75.75 0 0112 18zM3.75 6.75h1.5a.75.75 0 100-1.5h-1.5a.75.75 0 000 1.5zM5.25 18.75h-1.5a.75.75 0 010-1.5h1.5a.75.75 0 010 1.5zM3 12a.75.75 0 01.75-.75h7.5a.75.75 0 010 1.5h-7.5A.75.75 0 013 12zM9 3.75a2.25 2.25 0 100 4.5 2.25 2.25 0 000-4.5zM12.75 12a2.25 2.25 0 114.5 0 2.25 2.25 0 01-4.5 0zM9 15.75a2.25 2.25 0 100 4.5 2.25 2.25 0 000-4.5z" />
                    </svg>
                    <h1 class="text-[#484848] text-[12px] font-medium leading-4">Filter</h1>
                </button>
                <div class="hidden absolute md:w-[1030px] left-0 top-0 h-full md:flex justify-between md:items-center max-md:-top-8 md:pl-8 max-md:px-4 swipe-buttons">
                    <div class="relative flex h-full items-center btn-prev">
                        <button type="button" @click="scrollToPrev()" class="p-2 flex justify-center items-center bg-white border relative rounded-full border-gray-300 hover:scale-[1.1] z-50">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000" class="w-4 h-4">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5"/>
                            </svg>
                        </button>
                    </div>
                    <div class="relative flex h-full  items-center btn-next">
                        <button type="button" @click="scrollToNext()" class="p-2 flex justify-center items-center bg-white border relative rounded-full border-gray-300 hover:scale-[1.1] z-50">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000" class="w-4 h-4">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    const { data: categories } = await useFetch('https://dummyjson.com/products/categories');

    let scrollToPrev = () => {
        const scrollCategory = document.querySelector(".category-scroll");
        scrollCategory.scrollLeft -= scrollCategory.offsetWidth / 4;
    }

    let scrollToNext = () => {
        const scrollCategory = document.querySelector(".category-scroll");
        scrollCategory.scrollLeft += scrollCategory.offsetWidth / 4;
    }  
</script>

<style>
    .category-scroll::-webkit-scrollbar{
        display: none;
    }
</style>