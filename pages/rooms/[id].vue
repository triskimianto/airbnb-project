<template>
    <div class="mx-4 md:mx-[116px] my-7">
        <section>
            <h1 class="text-[24px] font-medium">{{ selectedId.title }}</h1>
            <div class="flex flex-row justify-between items-center mt-2">
                <div class="flex flex-row gap-x-1 items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
                        <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                    </svg>
                    <h1>{{ selectedId.rating }}</h1>
                    <span>·</span>
                    <NuxtLink to="#">2 Ulasan</NuxtLink>
                    <span>·</span>
                    <h1>HosTeladan</h1>
                    <span>·</span>
                    <NuxtLink to="#">{{ selectedId.country }}</NuxtLink>
                </div>
                <div class="flex justify-between gap-x-5">
                    <NuxtLink to="#" class="flex flex-row items-center gap-x-1">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
                            <path fill-rule="evenodd" d="M11.47 2.47a.75.75 0 011.06 0l4.5 4.5a.75.75 0 01-1.06 1.06l-3.22-3.22V16.5a.75.75 0 01-1.5 0V4.81L8.03 8.03a.75.75 0 01-1.06-1.06l4.5-4.5zM3 15.75a.75.75 0 01.75.75v2.25a1.5 1.5 0 001.5 1.5h13.5a1.5 1.5 0 001.5-1.5V16.5a.75.75 0 011.5 0v2.25a3 3 0 01-3 3H5.25a3 3 0 01-3-3V16.5a.75.75 0 01.75-.75z" clip-rule="evenodd" />
                        </svg>
                        <span>Bagikan</span>
                    </NuxtLink>
                    <NuxtLink to="#" class="flex flex-row items-center gap-x-1">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
                        </svg>
                        <span>Simpan</span>
                    </NuxtLink>
                </div>
            </div>
            <div class="flex flex-row w-full gap-x-2 mt-6">
                <div class="w-1/2">
                    <img class="w-full h-full rounded-l-[12px]" :src="selectedId.src" :alt="selectedId.alt">
                </div>
                <div class="w-1/2 grid grid-cols-2 gap-2">
                    <img class="w-full h-full" :src="selectedId.src" :alt="selectedId.alt">
                    <img class="w-full h-full rounded-tr-[12px]" :src="selectedId.src" :alt="selectedId.alt">
                    <img class="w-full h-full" :src="selectedId.src" :alt="selectedId.alt">
                    <img class="w-full h-full rounded-br-[12px]" :src="selectedId.src" :alt="selectedId.alt">
                </div>
                <!-- <button class="absolute top-[540px] right-0 mr-36 bg-white border border-[#484848] rounded-lg px-4 py-1 ">
                    <span>Tampilkan semua foto</span>
                </button> -->
            </div>                
        </section>
        <section class="flex flex-row justify-between items-center mt-10">
            <div class="w-2/3">
                <div class="mr-[100px]">
                    <div class="flex flex-row justify-between items-center">
                        <h1>Kamar di rumah. Tuan rumah: Nama</h1>
                        <img class="w-10 h-10 rounded-full" src="/Rectangle 4.png" alt="">
                    </div>
                    <div class="flex flex-row justify-between items-center mt-4">
                        <div class="w-[206px] h-[88px] border rounded-[12px] px-4 py-6">
                            <div class="flex flex-row">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                </svg>
                                <h1>1 tempat tidur ganda</h1>
                            </div>                            
                        </div>
                        <div class="w-[206px] h-[88px] border rounded-[12px] px-4 py-6">
                            <div class="flex flex-row">                            
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                </svg>
                                <h1>Kamar mandi khusus di luar kamar</h1>
                            </div>
                        </div>
                        <div class="w-[206px] h-[88px] border rounded-[12px] px-4 py-6">
                            <div class="flex flex-row">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                                </svg>
                                <h1>Mungkin ada tamu lain di sini</h1>
                            </div>
                        </div>
                    </div>
                    <hr class="h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">
                    <div>
                        <div class="flex flex-row">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                            </svg>
                            <div class="flex flex-col">
                                <h1>Kamar di rumah liburan</h1>
                                <p>Kamar Anda sendiri di dalam rumah, serta akses ke ruang bersama.</p>
                            </div>
                        </div>
                        <div class="flex flex-row">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                            </svg>
                            <div class="flex flex-col">
                                <h1>Area kerja khusus</h1>
                                <p>Area bersama dengan wifi yang cocok untuk bekerja.</p>
                            </div>
                        </div>
                        <div class="flex flex-row">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
                            </svg>
                            <div class="flex flex-col">
                                <h1>Sri adalah seorang HosTeladan.</h1>
                                <p>HosTeladan adalah tuan rumah berpengalaman dan berpenilaian tinggi yang berkomitmen dalam menyediakan penginapan luar biasa bagi tamu.</p>
                            </div>
                        </div>
                    </div>
                    <hr class="h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">
                    <div>
                        <p>Beberapa info diterjemahkan secara otomatis. <span>Tampilkan bahasa asli</span></p>
                    </div>
                    <hr class="h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">
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
                    <hr class="h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">
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
                    <hr class="h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">
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
                    <hr class="h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">                    
                </div>                                
                <div>ps: it's a datepicker</div>
            </div>
            <div class="w-1/3">
                <div class="w-full bg-white border rounded-[12px] shadow-lg">
                    <div class="px-6 py-[30px]">
                        <div class="flex flex-row justify-between items-end">
                            <h1 class="text-[24px]">577€<span class="text-[18px]">malam</span></h1>    
                            <div class="flex gap-x-2">
                                <h1>{{ selectedId.rating }}</h1>
                                <span>·</span>
                                <NuxtLink to="#">2 Ulasan</NuxtLink>
                            </div>                        
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section>
            <hr class="w-full h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">   
            <div class="flex gap-x-2">
                <h1>{{ selectedId.rating }}</h1>
                <span>·</span>
                <NuxtLink to="#">2 Ulasan</NuxtLink>
            </div>   
            <div>
                review section
            </div>             
        </section>
        <section>
            <hr class="w-full h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">   
            <div class="flex flex-col">
                <h1>Lokasi Anda</h1>
                <p>maps section</p>                
            </div>   
        </section>
        <section>
            <hr class="w-full h-px my-6 bg-gray-200 border-0 dark:bg-gray-700">   
            <div class="flex flex-col">
                <h1>Hal yang perlu diketahui</h1>
                <p>further information</p>                
            </div>   
        </section>
    </div>
</template>

<script setup>
    let rooms = [
        {
            id: 1,
            src: "/images/discover-1.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Cayman Islands",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Houses",
        },
        {
            id: 2,
            src: "/images/discover-2.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Uruguay",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Houses",
        },
        {
            id: 3,
            src: "/images/discover-3.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Iceland",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Houses",
        },
        {
            id: 4,
            src: "/images/discover-4.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Mongolia",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Houses",
        },
        {
            id: 5,
            src: "/images/discover-5.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Bahrain",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Houses",
        },
        {
            id: 6,
            src: "/images/discover-6.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Bosnia and Herzegovina",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Houses",
        },
        {
            id: 7,
            src: "/images/accomodations-1.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "Toledo",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 8,
            src: "/images/accomodations-2.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "Mesa",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 9,
            src: "/images/accomodations-3.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "Utica",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 10,
            src: "/images/accomodations-4.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "South Bend",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 11,
            src: "/images/accomodations-5.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "Toledo",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 12,
            src: "/images/accomodations-6.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "Mesa",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 13,
            src: "/images/accomodations-7.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "Utica",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 14,
            src: "/images/accomodations-8.png",
            alt: "À partir de 577€/personne - 3 jours",
            city: "South Bend",
            rating: "4,98",
            desc: "À partir de 577€/personne - 3 jours",
            category: "Experiences",
        },
        {
            id: 15,
            src: "/images/experiences-1.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Cayman Islands",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Adventures",
        },
        {
            id: 16,
            src: "/images/experiences-2.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Uruguay",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Adventures",
        },
        {
            id: 17,
            src: "/images/experiences-3.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Iceland",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Adventures",
        },
        {
            id: 18,
            src: "/images/experiences-4.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Mongolia",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Adventures",
        },
        {
            id: 19,
            src: "/images/experiences-5.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Bahrain",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Adventures",
        },
        {
            id: 20,
            src: "/images/experiences-6.png",
            alt: "2 Nights PACKAGE All Inclusive",
            country: "Bosnia and Herzegovina",
            title: "2 Nights PACKAGE All Inclusive",
            desc: "À partir de 577€/personne - 3 jours",
            rating: "5.0",
            category: "Adventures",
        },
    ];

    const route = useRoute();
    const selectedId = rooms.filter((r) => r.id == route.params.id)[0];

    useHead({
        title: selectedId.title,
    });
</script>