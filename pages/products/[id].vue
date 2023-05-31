<template>
    <div>
        <div>
            <SecondNavbar />
        </div>
        <div class="w-[388px] md:w-[1120px] mx-auto my-7">
            <section>
                <h1 class="text-[24px] font-medium">{{ selectedId.title }}</h1>
                <div class="flex flex-row justify-between items-center mt-2">
                    <div class="flex flex-row gap-x-2 items-center">
                        <div class="flex items-center gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
                                <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                            </svg>
                            <h1 class="text-[14px] font-normal">{{ selectedId.rating.rate }}</h1>
                            <span>·</span>
                            <NuxtLink to="#" class="text-[14px] font-normal underline">{{ selectedId.rating.count }} Ulasan</NuxtLink>                            
                        </div>
                        <span>·</span>        
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-3 h-3">
                            <path fill-rule="evenodd" d="M5.166 2.621v.858c-1.035.148-2.059.33-3.071.543a.75.75 0 00-.584.859 6.753 6.753 0 006.138 5.6 6.73 6.73 0 002.743 1.346A6.707 6.707 0 019.279 15H8.54c-1.036 0-1.875.84-1.875 1.875V19.5h-.75a2.25 2.25 0 00-2.25 2.25c0 .414.336.75.75.75h15a.75.75 0 00.75-.75 2.25 2.25 0 00-2.25-2.25h-.75v-2.625c0-1.036-.84-1.875-1.875-1.875h-.739a6.706 6.706 0 01-1.112-3.173 6.73 6.73 0 002.743-1.347 6.753 6.753 0 006.139-5.6.75.75 0 00-.585-.858 47.077 47.077 0 00-3.07-.543V2.62a.75.75 0 00-.658-.744 49.22 49.22 0 00-6.093-.377c-2.063 0-4.096.128-6.093.377a.75.75 0 00-.657.744zm0 2.629c0 1.196.312 2.32.857 3.294A5.266 5.266 0 013.16 5.337a45.6 45.6 0 012.006-.343v.256zm13.5 0v-.256c.674.1 1.343.214 2.006.343a5.265 5.265 0 01-2.863 3.207 6.72 6.72 0 00.857-3.294z" clip-rule="evenodd" />
                        </svg>
                        <h1 class="text-[14px] font-light">HosTeladan</h1>
                        <span>·</span>
                        <NuxtLink to="#" class="text-[14px] font-normal underline">{{ selectedId.category }}</NuxtLink>
                    </div>
                    <div class="flex justify-between items-center gap-x-5">
                        <NuxtLink to="#" class="flex flex-row items-center gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
                                <path fill-rule="evenodd" d="M11.47 2.47a.75.75 0 011.06 0l4.5 4.5a.75.75 0 01-1.06 1.06l-3.22-3.22V16.5a.75.75 0 01-1.5 0V4.81L8.03 8.03a.75.75 0 01-1.06-1.06l4.5-4.5zM3 15.75a.75.75 0 01.75.75v2.25a1.5 1.5 0 001.5 1.5h13.5a1.5 1.5 0 001.5-1.5V16.5a.75.75 0 011.5 0v2.25a3 3 0 01-3 3H5.25a3 3 0 01-3-3V16.5a.75.75 0 01.75-.75z" clip-rule="evenodd" />
                            </svg>
                            <span class="text-[14px] font-normal underline">Bagikan</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex flex-row items-center gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
                            </svg>
                            <span class="text-[14px] font-normal underline">Simpan</span>
                        </NuxtLink>
                    </div>
                </div>
                <div class="flex w-full max-h-[334px] justify-between items-center rounded-[12px] overflow-hidden gap-x-2 mt-7">
                    <div class="w-full md:w-1/2 h-[334px] overflow-hidden">
                        <img :src="selectedId.image" class="h-[334px] w-full object-cover" alt="" />
                    </div>
                    <div class="hidden md:flex flex-col w-1/2 h-[334px] justify-between gap-y-2">
                        <div class="flex gap-x-2">
                            <img :src="selectedId.image" class="w-1/2 h-[163px] object-cover" alt="">
                            <img :src="selectedId.image" class="w-1/2 h-[163px] object-cover" alt="">
                        </div>
                        <div class="flex gap-x-2">
                            <img :src="selectedId.image" class="w-1/2 h-[163px] object-cover" alt="">
                            <img :src="selectedId.image" class="w-1/2 h-[163px] object-cover" alt="">
                        </div>
                    </div>
                </div>            
            </section>
            <section class="flex flex-row justify-between mt-12">
                <div class="w-2/3">
                    <div class="mr-[100px]">
                        <div class="flex flex-row justify-between items-center">
                            <h1 class="text-[24px] font-normal">Kamar di rumah. Tuan rumah: Nama</h1>
                            <img class="w-10 h-10 rounded-full" :src="selectedId.image" alt="">
                        </div>
                        <div class="flex flex-row justify-between items-center mt-4">
                            <div class="w-[206px] h-[88px] border borde-[#c4c4c4] rounded-[12px] px-4 py-4">
                                <div class="flex flex-row w-[140px] mx-auto align-center items-center gap-x-2">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                    </svg>
                                    <h1 class="text-[16px] leading-[18px]">1 tempat tidur ganda</h1>
                                </div>                            
                            </div>
                            <div class="w-[206px] h-[88px] border rounded-[12px] px-4 py-4">
                                <div class="flex flex-row w-[140px] mx-auto align-center items-center gap-x-2">                            
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                    </svg>
                                    <h1 class="text-[16px] leading-[18px]">Kamar mandi khusus di luar kamar</h1>
                                </div>
                            </div>
                            <div class="w-[206px] h-[88px] border rounded-[12px] px-4 py-4">
                                <div class="flex flex-row w-[140px] mx-auto align-center gap-x-2">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                    </svg>
                                    <h1 class="text-[16px] leading-[18px]">Mungkin ada tamu lain di sini</h1>
                                </div>
                            </div>
                        </div>
                        <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                        <div>
                            <div class="flex flex-row">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                </svg>
                                <div class="flex flex-col">
                                    <h1 class="text-[16px] font-medium leading-[18px]">Kamar di rumah liburan</h1>
                                    <p class="text-[14px] font-light leading-[15px]">Kamar Anda sendiri di dalam rumah, serta akses ke ruang bersama.</p>
                                </div>
                            </div>
                            <div class="flex flex-row">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                </svg>
                                <div class="flex flex-col">
                                    <h1 class="text-[16px] font-medium leading-[18px]">Area kerja khusus</h1>
                                    <p class="text-[14px] font-light leading-[15px]">Area bersama dengan wifi yang cocok untuk bekerja.</p>
                                </div>
                            </div>
                            <div class="flex flex-row">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                </svg>
                                <div class="flex flex-col">
                                    <h1 class="text-[16px] font-medium leading-[18px]">Sri adalah seorang HosTeladan.</h1>
                                    <p class="text-[14px] font-light leading-[15px]">HosTeladan adalah tuan rumah berpengalaman dan berpenilaian tinggi yang berkomitmen dalam menyediakan penginapan luar biasa bagi tamu.</p>
                                </div>
                            </div>
                        </div>
                        <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                        <div>
                            <p>Beberapa info diterjemahkan secara otomatis. <span>Tampilkan bahasa asli</span></p>
                        </div>
                        <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                        <div>
                            <h1>Tuan rumah Anda</h1>
                            <div class="bg-gray-200 rounded-[16px] px-[136px]">
                                <div class="w-[380px]">
                                    <div class="w-full bg-white">
                                        <h1>A</h1>
                                    </div>
                                    <div class="w-full">
                                        <p>Pekerjaan saya: Pensiunan warga sipil</p>
                                        <p>Pekerjaan saya: Pensiunan warga sipil</p>
                                        <p>Pekerjaan saya: Pensiunan warga sipil</p>
                                    </div>
                                </div>                            
                            </div>
                        </div>
                        <div>
                            <h1>Tentang tempat ini</h1>
                            <p>Kamar tidur bergaya Tatami ini cocok untuk 2 orang. Guesthouse ini memiliki 2 lantai yang terletak di kawasan Perumahan Wirobrajan. Semua 3 kamar pribadi terletak di lantai 2 bersama dengan fasilitas bersama; pantry, meja makan, lounge, galeri kecil & teras. Lantai 1 adalah tempat orang tua saya kadang-kadang menghabiskan waktu mereka. Di Lt 1 juga terdapat dapur, kolam ikan, dan beberapa area bersama yang dapat Anda gunakan. Suasana lingkungan aman dan sangat dekat dengan pusat kota...</p>
                            <div class="flex flex-row items-center">
                                <h1>Tampilkan lebih banyak</h1>
                                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                                    <path fill-rule="evenodd" d="M16.28 11.47a.75.75 0 010 1.06l-7.5 7.5a.75.75 0 01-1.06-1.06L14.69 12 7.72 5.03a.75.75 0 011.06-1.06l7.5 7.5z" clip-rule="evenodd" />
                                </svg>
                            </div>
                        </div>
                        <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                        <div>
                            <div class="w-[206px] h-full border rounded-[12px] px-4 py-6">
                                <div class="flex flex-col">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                    </svg>
                                    <h1>Kamar tidur</h1>
                                    <p>1 tempat tidur ganda</p>
                                </div>                            
                            </div>
                        </div>
                        <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                        <div>
                            <div class="flex flex-col">
                                <h1>Fasilitas yang ditawarkan</h1>
                                <div class="grid grid-cols-2">
                                    <div class="flex flex-row">
                                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                        </svg>
                                        <h1>Kunci pada pintu kamar tidur</h1>
                                    </div>
                                    <div class="flex flex-row">
                                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                        </svg>
                                        <h1>Kunci pada pintu kamar tidur</h1>
                                    </div>
                                    <div class="flex flex-row">
                                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                        </svg>
                                        <h1>Kunci pada pintu kamar tidur</h1>
                                    </div>
                                    <div class="flex flex-row">
                                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                        </svg>
                                        <h1>Kunci pada pintu kamar tidur</h1>
                                    </div>
                                </div>                        
                            </div>
                            <button class="border border-[#484848] rounded-lg px-6 py-3">
                                Tampilkan ke-xx fasilitas
                            </button>
                        </div>
                        <hr class="h-px my-6 bg-[#c4c4c4] border-0">               
                    </div>                                
                    <div>ps: it's a datepicker</div>
                </div>
                <div class="w-1/3">
                    <div class="w-full bg-white border rounded-[12px] shadow-lg">
                        <div class="px-6 py-[30px]">
                            <div class="flex flex-row-reverse justify-between items-end">                                
                                <div class="flex gap-x-1">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4 my-[2px]">
                                        <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                                    </svg>
                                    <h1 class="text-[16px] font-light">{{ selectedId.rating.rate }}</h1>
                                    <span>·</span>
                                    <NuxtLink to="#" class="text-[16px] font-light">{{ selectedId.rating.count }} Ulasan</NuxtLink>                                    
                                </div>                        
                                <h1 class="text-[24px] font-medium">Rp {{ formatPrice(selectedId.price * 14996) }}<span class="text-[16px] font-light">malam</span></h1>    
                            </div>
                            <div class="flex mt-6">
                                form 1
                            </div>
                            <div class="flex mt-6">
                                form 2
                            </div>
                            <div class="mt-4">
                                <MainCTA :to="`/book/${id}`" :btnTitle="btnTitle" />
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            <section>
                <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                <div class="flex gap-x-2">
                    <h1>{{ selectedId.rating.rate }}</h1>
                    <span>·</span>
                    <NuxtLink to="#">{{ selectedId.rating.count }} Ulasan</NuxtLink>
                </div>   
                <div>
                    review section
                </div>             
            </section>
            <section>
                <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                <div class="flex flex-col">
                    <h1>Lokasi Anda</h1>
                    <p>maps section</p>                
                </div>   
            </section>
            <section>
                <hr class="h-px my-6 bg-[#c4c4c4] border-0">
                <div class="flex flex-col">
                    <h1>Hal yang perlu diketahui</h1>
                    <p>further information</p>                
                </div>   
            </section>
        </div>
    </div>
</template>

<script setup>
    
    const btnTitle = "Pesan";
    
    const route = useRoute();
    const id = route.params.id;
    const { data: selectedId } = await useFetch('https://fakestoreapi.com/products/'+id);

    let formatPrice = (price) => {
        let result = Math.floor(price)
        return result.toLocaleString('id-ID', { useGrouping: true })
    };

    useHead({
        title: selectedId.title,
    });

</script>
