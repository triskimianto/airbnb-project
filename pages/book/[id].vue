<template>
    <div>
        <div class="w-full h-[80px] bg-white shadow px-6 py-6">
            <NuxtLink to="/">
                <img :src="navBrandSrc" alt="airbnb">
            </NuxtLink>
        </div>
        <div class="flex w-[1160px] mx-auto justify-between items-center mt-[70px]">
            <NuxtLink :to="`/products/${id}`">
                <button class="w-10 h-10 hover:bg-gray-100 rounded-full p-1.5">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                        <path fill-rule="evenodd" d="M7.72 12.53a.75.75 0 010-1.06l7.5-7.5a.75.75 0 111.06 1.06L9.31 12l6.97 6.97a.75.75 0 11-1.06 1.06l-7.5-7.5z" clip-rule="evenodd" />
                    </svg>
                </button>
            </NuxtLink>
            <div class="w-[1120px] mx-auto">                
                <h1 class="text-[32px] font-medium leading-9">Ajukan Pemesanan</h1>
            </div>
        </div>
        <div class="flex w-[1120px] mx-auto pl-[20px] mt-[48px]">            
            <div class="w-[560px]">
                <section>
                    <div class="flex flex-col">
                        <h1 class="text-[22px] font-medium leading-6">Perjalanan Anda</h1>
                        <div>
                            <div>
                                <h1 class="text-[16px] font-medium leading-5">Tanggal</h1>
                                <h1 class="text-[16px] font-light leading-5">21-23 Jun</h1> 
                            </div>
                            <div>
                                <h1 class="text-[16px] font-medium leading-5 underline">Edit</h1>
                            </div>
                        </div>
                        <div>
                            <div>
                                <h1 class="text-[16px] font-medium leading-5">Tamu</h1>
                                <h1 class="text-[16px] font-light leading-5">1 Tamu</h1> 
                            </div>
                            <div>
                                <h1 class="text-[16px] font-medium leading-5 underline">Edit</h1>
                            </div>
                        </div>
                    </div>
                    <hr>
                </section>                
                <section>
                    <div>
                        <h1 class="text-[22px] font-medium leading-[26px]">Masuk ke akun atau daftar untuk memesan</h1>
                        <div>form</div>
                    </div>
                </section>
            </div>
            <div class="w-[466.656px] ml-[93.3281px]">
                <div class="w-full border border-gray-200 rounded-[12px] p-6">
                    <div class="flex w-full">
                        <img class="w-[124px] h-[106px] object-cover rounded-[8px]" :src="recSrc" alt="">
                        <div class="ml-3">
                            <div>
                                <h1 class="text-[#c4c4c4] text-[12px] leading-4">Kamar di rumah liburan</h1>
                                <h1 class="text-[#484848] text-[14px] leading-[18px] mt-1">Book for id: {{ id }} - {{ selectedId.title }}</h1>
                            </div>
                        </div>
                    </div>                    
                </div>
                
            </div>
        </div>
    </div>    
</template>

<script setup>
    import navBrandSrc from '/icons/airbnb-nav-red-text.png';
    import recSrc from '/Rectangle 4.png';

    const route = useRoute();
    const id = route.params.id;
    const { data:selectedId } = await useFetch('https://fakestoreapi.com/products/'+id);

</script>