<template>
    <div>
        <div>
            <SecondNavbar />
        </div>
        <div class="w-[388px] md:w-[1120px] mx-auto mt-7 mb-[64px]">
            <section>
                <h1 class="text-[#484848] text-[26px] font-medium leading-[30px]"><span>{{ selectedId.brand }}</span> - {{ selectedId.title }}</h1>
                <div class="flex flex-row justify-between items-center mt-2">
                    <div class="flex flex-row gap-x-2 items-center">
                        <div class="flex items-center gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-4 h-4">
                                <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                            </svg>
                            <h1 class="text-[#484848] text-[14px] font-medium leading-5">{{ selectedId.rating }}</h1>
                            <span class="text-[#484848] text-[14px] font-medium leading-5">·</span>
                            <button class="text-[#484848] text-[14px] font-medium leading-5 underline">{{ selectedId.rating.count }} Ulasan</button>                            
                        </div>
                        <span>·</span>                              
                        <button class="text-[#484848] text-[14px] font-medium leading-5 underline">{{ selectedId.category }}</button>
                    </div>
                    <div class="flex justify-between items-center gap-x-5">
                        <button class="flex flex-row items-center gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
                                <path fill-rule="evenodd" d="M11.47 2.47a.75.75 0 011.06 0l4.5 4.5a.75.75 0 01-1.06 1.06l-3.22-3.22V16.5a.75.75 0 01-1.5 0V4.81L8.03 8.03a.75.75 0 01-1.06-1.06l4.5-4.5zM3 15.75a.75.75 0 01.75.75v2.25a1.5 1.5 0 001.5 1.5h13.5a1.5 1.5 0 001.5-1.5V16.5a.75.75 0 011.5 0v2.25a3 3 0 01-3 3H5.25a3 3 0 01-3-3V16.5a.75.75 0 01.75-.75z" clip-rule="evenodd" />
                            </svg>
                            <span class="text-[#484848] text-[14px] font-medium leading-5 underline">Bagikan</span>
                        </button>
                        <button class="flex flex-row items-center gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
                            </svg>
                            <span class="text-[#484848] text-[14px] font-medium leading-5 underline">Simpan</span>
                        </button>
                    </div>
                </div>
                <div v-if="selectedId.images.length == 1" class="flex w-full max-h-[334px] justify-between items-center gap-x-2 mt-7">
                    <div class="w-full h-[334px] overflow-hidden ">
                        <div class="img-container overflow-hidden hover:rounded-[12px] cursor-pointer" @click="openModal">
                            <img :src="selectedId.images !== null ? selectedId.images[0] : selectedId.thumbnail" class="h-[334px] w-full object-contain border rounded-[12px]" :alt="selectedId.title" />                        
                        </div>                        
                    </div>                    
                </div>    
                <div v-if="selectedId.images.length == 2" class="flex w-full max-h-[334px] justify-between items-center gap-x-2 mt-7">
                    <div class="w-full md:w-1/2 h-[334px] overflow-hidden ">
                        <div class="img-container overflow-hidden hover:rounded-l-[12px] cursor-pointer" @click="openModal">
                            <img :src="selectedId.images !== null ? selectedId.images[0] : selectedId.thumbnail" class="h-[334px] w-full object-contain border rounded-l-[12px]" :alt="selectedId.title" />                        
                        </div>
                    </div>
                    <div class="hidden md:flex flex-col w-1/2 h-[334px] justify-between gap-y-2">                        
                        <div class="flex">
                            <div class="img-container overflow-hidden hover:rounded-r-[12px] cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[1] !== null ? selectedId.images[1] : selectedId.thumbnail" class="w-[552px] h-[334px] object-contain border rounded-r-[12px]" :alt="selectedId.title">                                          
                            </div>
                            <button class="absolute ml-[326px] mt-[276px] bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[15px] py-[7px] z-10">
                                <div class="flex w-[167px] justify-between">
                                    <svg viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="presentation" focusable="false" class="w-4 h-4" fill="currentColor">
                                        <path d="m3 11.5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3z" fill-rule="evenodd"></path>
                                    </svg>
                                    <h1 class="text-[#484848] text-[14px] font-medium leading-[18px]" @click="openModal">Tampilkan semua foto</h1>
                                </div>
                            </button>
                        </div>
                    </div>
                </div>                       
                <div v-if="selectedId.images.length == 3" class="flex w-full max-h-[334px] justify-between items-center gap-x-2 mt-7">
                    <div class="w-full md:w-1/2 h-[334px] overflow-hidden ">
                        <div class="img-container overflow-hidden hover:rounded-l-[12px] cursor-pointer" @click="openModal">
                            <img :src="selectedId.images !== null ? selectedId.images[0] : selectedId.thumbnail" class="h-[334px] w-full object-contain border rounded-l-[12px]" :alt="selectedId.title" />                        
                        </div>
                    </div>
                    <div class="hidden md:flex flex-col w-1/2 h-[334px] justify-between gap-y-2">
                        <div class="flex gap-x-2">                            
                            <div class="img-container overflow-hidden hover:rounded-tr-[12px] cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[1] !== null ? selectedId.images[1] : selectedId.thumbnail" class="w-[552px] h-[163px] object-contain border rounded-tr-[12px]" :alt="selectedId.title">                                                        
                            </div>
                        </div>
                        <div class="flex">
                            <div class="img-container overflow-hidden hover:rounded-br-[12px] cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[2] !== null ? selectedId.images[2] : selectedId.thumbnail" class="w-[552px] h-[163px] object-contain border rounded-br-[12px]" :alt="selectedId.title">                                          
                            </div>
                            <button class="absolute ml-[326px] mt-[104px] bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[15px] py-[7px] z-10">
                                <div class="flex w-[167px] justify-between">
                                    <svg viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="presentation" focusable="false" class="w-4 h-4" fill="currentColor">
                                        <path d="m3 11.5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3z" fill-rule="evenodd"></path>
                                    </svg>
                                    <h1 class="text-[#484848] text-[14px] font-medium leading-[18px]" @click="openModal">Tampilkan semua foto</h1>
                                </div>
                            </button>
                        </div>
                    </div>
                </div>                       
                <div v-if="selectedId.images.length == 4" class="flex w-full max-h-[334px] justify-between items-center gap-x-2 mt-7">
                    <div class="w-full md:w-1/2 h-[334px] overflow-hidden ">
                        <div class="img-container overflow-hidden hover:rounded-l-[12px] cursor-pointer" @click="openModal">
                            <img :src="selectedId.images !== null ? selectedId.images[0] : selectedId.thumbnail" class="h-[334px] w-full object-contain border rounded-l-[12px]" :alt="selectedId.title" />                        
                        </div>
                    </div>
                    <div class="hidden md:flex flex-col w-1/2 h-[334px] justify-between gap-y-2">
                        <div class="flex gap-x-2">       
                            <div class="img-container overflow-hidden cursor-pointer" @click="openModal">                     
                                <img :src="selectedId.images[1] !== null ? selectedId.images[1] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border" :alt="selectedId.title">                            
                            </div>
                            <div class="img-container overflow-hidden hover:rounded-tr-[12px] cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[2] !== null ? selectedId.images[2] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border rounded-tr-[12px]" :alt="selectedId.title">
                            </div>
                        </div>
                        <div class="flex">
                            <div class="img-container overflow-hidden hover:rounded-br-[12px] cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[3] !== null ? selectedId.images[3] : selectedId.thumbnail" class="w-[552px] h-[163px] object-contain border rounded-br-[12px]" :alt="selectedId.title">                                          
                            </div>
                            <button class="absolute ml-[326px] mt-[104px] bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[15px] py-[7px] z-10">
                                <div class="flex w-[167px] justify-between">
                                    <svg viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="presentation" focusable="false" class="w-4 h-4" fill="currentColor">
                                        <path d="m3 11.5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3z" fill-rule="evenodd"></path>
                                    </svg>
                                    <h1 class="text-[#484848] text-[14px] font-medium leading-[18px]" @click="openModal">Tampilkan semua foto</h1>
                                </div>
                            </button>
                        </div>
                    </div>
                </div>                       
                <div v-if="selectedId.images.length == 5" class="flex w-full max-h-[334px] justify-between items-center gap-x-2 mt-7">
                    <div class="w-full md:w-1/2 h-[334px] overflow-hidden ">
                        <div class="img-container overflow-hidden hover:rounded-l-[12px] cursor-pointer" @click="openModal">
                            <img :src="selectedId.images !== null ? selectedId.images[0] : selectedId.thumbnail" class="h-[334px] w-full object-contain border rounded-l-[12px]" :alt="selectedId.title" />                        
                        </div>
                    </div>
                    <div class="hidden md:flex flex-col w-1/2 h-[334px] justify-between gap-y-2">
                        <div class="flex gap-x-2">  
                            <div class="img-container overflow-hidden cursor-pointer" @click="openModal">                          
                                <img :src="selectedId.images[1] !== null ? selectedId.images[1] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border" :alt="selectedId.title">                            
                            </div>
                            <div class="img-container overflow-hidden hover:rounded-tr-[12px] cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[2] !== null ? selectedId.images[2] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border rounded-tr-[12px]" :alt="selectedId.title">
                            </div>
                        </div>
                        <div class="flex gap-x-2">
                            <div class="img-container overflow-hidden cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[3] !== null ? selectedId.images[3] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border" :alt="selectedId.title">              
                            </div>
                            <div class="flex">
                                <div class="img-container overflow-hidden hover:rounded-br-[12px] cursor-pointer" @click="openModal">
                                    <img :src="selectedId.images[4] !== null ? selectedId.images[4] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border rounded-br-[12px]" :alt="selectedId.title">
                                </div>
                                <button class="absolute mt-[104px] ml-[48px] bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[15px] py-[7px] z-10">
                                    <div class="flex w-[167px] justify-between">
                                        <svg viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="presentation" focusable="false" class="w-4 h-4" fill="currentColor">
                                            <path d="m3 11.5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3z" fill-rule="evenodd"></path>
                                        </svg>
                                        <h1 class="text-[#484848] text-[14px] font-medium leading-[18px]" @click="openModal">Tampilkan semua foto</h1>
                                    </div>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>            
                <div v-if="selectedId.images.length > 5" class="flex w-full max-h-[334px] justify-between items-center gap-x-2 mt-7">
                    <div class="w-full md:w-1/2 h-[334px] overflow-hidden ">
                        <div class="img-container overflow-hidden hover:rounded-l-[12px] cursor-pointer" @click="openModal">
                            <img :src="selectedId.images !== null ? selectedId.images[0] : selectedId.thumbnail" class="h-[334px] w-full object-contain border rounded-l-[12px]" :alt="selectedId.title" />                        
                        </div>
                    </div>
                    <div class="hidden md:flex flex-col w-1/2 h-[334px] justify-between gap-y-2">
                        <div class="flex gap-x-2">  
                            <div class="img-container overflow-hidden cursor-pointer" @click="openModal">                          
                                <img :src="selectedId.images[1] !== null ? selectedId.images[1] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border" :alt="selectedId.title">                            
                            </div>
                            <div class="img-container overflow-hidden hover:rounded-tr-[12px] cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[2] !== null ? selectedId.images[2] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border rounded-tr-[12px]" :alt="selectedId.title">
                            </div>
                        </div>
                        <div class="flex gap-x-2">
                            <div class="img-container overflow-hidden cursor-pointer" @click="openModal">
                                <img :src="selectedId.images[3] !== null ? selectedId.images[3] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border" :alt="selectedId.title">              
                            </div>
                            <div class="flex">
                                <div class="img-container overflow-hidden hover:rounded-br-[12px] cursor-pointer" @click="openModal">
                                    <img :src="selectedId.images[4] !== null ? selectedId.images[4] : selectedId.thumbnail" class="w-[272px] h-[163px] object-contain border rounded-br-[12px]" :alt="selectedId.title">
                                </div>
                                <button class="absolute mt-[104px] ml-[48px] bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[15px] py-[7px] z-10">
                                    <div class="flex w-[167px] justify-between">
                                        <svg viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="presentation" focusable="false" class="w-4 h-4" fill="currentColor">
                                            <path d="m3 11.5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm-10-5a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3zm5 0a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3z" fill-rule="evenodd"></path>
                                        </svg>
                                        <h1 class="text-[#484848] text-[14px] font-medium leading-[18px]" @click="openModal">Tampilkan semua foto</h1>
                                    </div>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>          
            </section>
            <section class="flex flex-col md:flex-row justify-between mt-12">
                <div class="w-full md:w-2/3">
                    <div class="md:mr-[100px] mb-6">
                        <div class="flex flex-col">
                            <h1 class="text-[#484848] text-[22px] font-medium leading-7">Rp {{ formatPrice(afterDiscount(selectedId.price,selectedId.discountPercentage)) }}</h1>
                            <div class="flex items-center gap-x-2 mt-1">
                                <div class="bg-[#ff5a5f] rounded px-1.5 py-1">
                                    <h1 class="text-white text-[10px] font-normal leading-[14px]">{{ selectedId.discountPercentage }} %</h1>
                                </div>
                                <h1 class="text-[#767676] text-[12px] font-normal leading-4"><s>Rp {{ formatPrice(normalPrice(selectedId.price)) }}</s></h1>
                            </div>
                        </div>                        
                        <hr class="h-px my-6 bg-gray-200 border-0">
                        <div class="flex flex-col gap-y-1">    
                            <div class="flex">
                                <h1 class="text-[#767676] text-[16px] font-normal leading-5">Produk:</h1>
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5 ml-1">{{ selectedId.title }}</h1>
                            </div>
                            <div class="flex">
                                <h1 class="text-[#767676] text-[16px] font-normal leading-5">Merek:</h1>
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5 ml-1">{{ selectedId.brand }}</h1>
                            </div>                
                            <div class="flex">
                                <h1 class="text-[#767676] text-[16px] font-normal leading-5">Kondisi:</h1>
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5 ml-1">Baru</h1>
                            </div>
                            <div class="flex">
                                <h1 class="text-[#767676] text-[16px] font-normal leading-5">Stok:</h1>
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5 ml-1">{{ selectedId.stock }}</h1>
                            </div>
                            <div class="flex">
                                <h1 class="text-[#767676] text-[16px] font-normal leading-5">Min. Pembelian:</h1>
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5 ml-1">1</h1>
                            </div>
                            <div class="flex">
                                <h1 class="text-[#767676] text-[16px] font-normal leading-5">Kategori:</h1>
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5 ml-1 underline">{{ selectedId.category }}</h1>
                            </div>
                        </div>
                        <div class="w-full mt-4">
                            <h1 class="text-[#484848] text-[16px] font-normal leading-5">{{ selectedId.description }}</h1>
                        </div>
                    </div>                        
                </div>
                <div class="w-full md:w-1/3">
                    <div class="w-full bg-white border rounded-[12px] shadow-lg">
                        <div class="px-6 py-[30px]">
                            <div class="flex flex-row-reverse justify-between items-end">                                
                                <div class="flex gap-x-1">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-4 h-4 mt-[1px]">
                                        <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                                    </svg>
                                    <h1 class="text-[#484848] text-[16px] font-normal leading-5">{{ selectedId.rating}}</h1>                                 
                                </div>                        
                                <h1 class="text-[#484848] text-[24px] font-medium leading-7">Rp {{ formatPrice(afterDiscount(selectedId.price,selectedId.discountPercentage)) }}</h1>    
                            </div>
                            <hr class="h-px my-6 bg-gray-200 border-0">
                            <div class="flex flex-col mt-6">
                                <div class="flex w-full justify-between items-center">
                                    <h1 class="text-[#484848] text-[16px] font-medium leading-5">Stok total:</h1>                                    
                                    <h1 class="text-[#484848] text-[16px] font-normal leading-5 px-4 py-2">{{ selectedId.stock }}</h1>                                                                            
                                </div>
                                <div class="flex w-full justify-between items-center">
                                    <h1 class="text-[#484848] text-[16px] font-medium leading-5">Jumlah:</h1>
                                    <div class="border border-gray-200 rounded-[4px]">
                                        <button class="bg-white hover:bg-gray-100 rounded-l-[4px] text-[#484848] text-[16px] font-normal leading-5 px-4 py-2" @click="decrement">-</button>
                                        <span class="text-[#484848] text-[16px] font-normal leading-5 px-4 py-2">{{ quantity }}</span>
                                        <button class="bg-white hover:bg-gray-100 rounded-r-[4px] text-[#484848] text-[16px] font-normal leading-5 px-4 py-2" @click="increment">+</button>
                                    </div>
                                </div>
                            </div>                    
                            <div class="mt-4">
                                <MainCTA :to="{ path: `/order/${id}`, query: { quantity }}" :btnTitle="btnTitle" />
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            <section>
                <hr class="h-px bg-gray-200 border-0 mt-8 mb-6">
                <div class="flex gap-x-2 items-center">
                    <div class="flex gap-x-1 items-center">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FF5A5F" class="w-6 h-6">
                            <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                        </svg>
                        <h1 class="text-[#484848] text-[22px] font-medium leading-[26px]">{{ selectedId.rating }}</h1>
                    </div>                    
                    <span class="text-[#484848] text-[22px] font-medium leading-[26px]">·</span>
                    <button class="text-[#484848] text-[22px] font-medium leading-[26px] underline"> Ulasan</button>                                                    
                </div>             
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-6">
                    <div class="flex flex-col">
                        <div class="flex items-center gap-x-2">
                            <img class="w-10 h-10 rounded-full" :src="rectSrc" alt="user-picture">
                            <div>
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5">User 1</h1>
                                <h1 class="text-[#767676] text-[12px] font-normal leading-4">Mei 2023</h1>
                            </div>
                        </div>
                        <h1 class="text-[#484848] text-[16px] font-normal leading-5 mt-4">Produk bagus. seller fast respon sesuai pesanan</h1>
                    </div>
                    <div class="flex flex-col">
                        <div class="flex items-center gap-x-2">
                            <img class="w-10 h-10 rounded-full" :src="rectSrc" alt="user-picture">
                            <div>
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5">User 2</h1>
                                <h1 class="text-[#767676] text-[12px] font-normal leading-4">Mei 2023</h1>
                            </div>
                        </div>
                        <h1 class="text-[#484848] text-[16px] font-normal leading-5 mt-4">Produk bagus. seller fast respon sesuai pesanan</h1>
                    </div>
                </div>
            </section>
            <section>
                <hr class="h-px bg-gray-200 border-0 mt-6 mb-8">
                <div class="w-full mt-[48px]">                
                    <h1 class="text-[#484848] text-[22px] font-medium leading-[26px] mt-6   ">Pilihan lainnya untuk Anda</h1>
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-6">
                        <MiniCardVer v-for="a in anotherProducts.products" :key="a.id" :to="`/products/${a.id}`" :src="a.thumbnail" :alt="a.title" :country="a.category" :title="'Rp '+formatPrice(a.price * 14900)" :desc="a.title" :rating="a.rating" />
                    </div>
                </div>
            </section>
        </div>
        <div>
            <footer class="bottom-0 left-0 z-20 w-full border-t bg-white py-3">
                <div class="w-[388px] md:w-[1120px] mx-auto">
                    <div class="flex flex-row justify-between items-center">
                        <div class="leading-[18.75px] text-[16px] text-[#484848] font-light">
                            <span>&copy; 2023 Airbnb, Inc.</span>
                        </div>
                    </div>
                </div>
            </footer>
        </div>
        <!-- images modal -->
        <div v-if="showModal" class="fixed inset-0 flex items-center justify-center z-50">
            <div class="absolute inset-0 bg-white">
                <div class="flex justify-between items-center px-4 py-4">
                    <button class="bg-white hover:bg-gray-100 rounded-full p-1.5" @click="closeModal">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-5 h-5">
                            <path fill-rule="evenodd" d="M7.72 12.53a.75.75 0 010-1.06l7.5-7.5a.75.75 0 111.06 1.06L9.31 12l6.97 6.97a.75.75 0 11-1.06 1.06l-7.5-7.5z" clip-rule="evenodd" />
                        </svg>
                    </button>
                    <div class="flex justify-between items-center gap-x-5">
                        <button class="flex flex-row items-center bg-white hover:bg-gray-100 rounded-[4px] p-1.5 gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#484848" class="w-4 h-4">
                                <path fill-rule="evenodd" d="M11.47 2.47a.75.75 0 011.06 0l4.5 4.5a.75.75 0 01-1.06 1.06l-3.22-3.22V16.5a.75.75 0 01-1.5 0V4.81L8.03 8.03a.75.75 0 01-1.06-1.06l4.5-4.5zM3 15.75a.75.75 0 01.75.75v2.25a1.5 1.5 0 001.5 1.5h13.5a1.5 1.5 0 001.5-1.5V16.5a.75.75 0 011.5 0v2.25a3 3 0 01-3 3H5.25a3 3 0 01-3-3V16.5a.75.75 0 01.75-.75z" clip-rule="evenodd" />
                            </svg>
                            <span class="text-[#484848] text-[14px] font-medium leading-5 underline">Bagikan</span>
                        </button>
                        <button class="flex flex-row items-center bg-white hover:bg-gray-100 rounded-[4px] p-1.5 gap-x-1">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="#484848" class="w-4 h-4">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
                            </svg>
                            <span class="text-[#484848] text-[14px] font-medium leading-5 underline">Simpan</span>
                        </button>
                    </div>
                </div>
                <div class="w-full max-h-screen overflow-y-auto pt-12 pb-[88px]">
                    <div class="flex flex-col w-[388px] md:w-[748px] 2xl:w-[1496px] mx-auto px-2">
                        <div v-for="(image, index) in selectedId.images" :key="index" class="flex justify-center items-center pb-4">
                            <div class="img-container overflow-hidden hover:rounded-[8px] cursor-pointer" @click="openImgViewer(index)">
                                <img class="object-cover border border-gray-200 rounded-[8px]" :src="image" :alt="'image-'+index">
                            </div>
                        </div>
                    </div>
                </div>
            </div>            
        </div>
        <!-- image viewer modal -->
        <div v-if="showImgViewer" class="fixed inset-0 flex items-center justify-center z-50">
            <div class="absolute inset-0 bg-black">
                <div class="flex justify-between items-center px-2 md:px-10 py-12">
                    <button class="flex items-center bg-black hover:bg-[#767676] rounded-[8px] gap-x-1 px-3 py-2" @click="closeImgViewer">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-5 h-5">
                            <path fill-rule="evenodd" d="M5.47 5.47a.75.75 0 011.06 0L12 10.94l5.47-5.47a.75.75 0 111.06 1.06L13.06 12l5.47 5.47a.75.75 0 11-1.06 1.06L12 13.06l-5.47 5.47a.75.75 0 01-1.06-1.06L10.94 12 5.47 6.53a.75.75 0 010-1.06z" clip-rule="evenodd" />
                        </svg>
                        <h1 class="text-white text-[14px] font-medium leading-[18px] mr-1">Tutup</h1>
                    </button>
                    <h1 class="text-white text-[14px] font-medium leading-[18px]">{{ selectedIndex + 1 }}<span> / {{ selectedId.images.length }}</span></h1>
                    <div class="flex justify-between items-center gap-x-1">
                        <button class="bg-black hover:bg-[#767676] rounded-full p-2">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-4 h-4">
                                <path fill-rule="evenodd" d="M11.47 2.47a.75.75 0 011.06 0l4.5 4.5a.75.75 0 01-1.06 1.06l-3.22-3.22V16.5a.75.75 0 01-1.5 0V4.81L8.03 8.03a.75.75 0 01-1.06-1.06l4.5-4.5zM3 15.75a.75.75 0 01.75.75v2.25a1.5 1.5 0 001.5 1.5h13.5a1.5 1.5 0 001.5-1.5V16.5a.75.75 0 011.5 0v2.25a3 3 0 01-3 3H5.25a3 3 0 01-3-3V16.5a.75.75 0 01.75-.75z" clip-rule="evenodd" />
                            </svg>                            
                        </button>
                        <button class="bg-black hover:bg-[#767676] rounded-full p-2">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="#FFFFFF" class="w-4 h-4">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
                            </svg>                            
                        </button>
                    </div>
                </div>
                <div class="flex w-[388px] md:w-[1300px] 2xl:w-[1854px] max-h-screen mx-auto justify-between items-center text-white pb-[114px]">
                    <button class="hidden md:flex bg-black hover:bg-[#767676] border-2 border-[#c4c4c4] rounded-full p-3" @click="prevImage">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-5 h-5">
                            <path fill-rule="evenodd" d="M7.72 12.53a.75.75 0 010-1.06l7.5-7.5a.75.75 0 111.06 1.06L9.31 12l6.97 6.97a.75.75 0 11-1.06 1.06l-7.5-7.5z" clip-rule="evenodd" />
                        </svg>
                    </button>      
                    <button class="absolute md:hidden ml-1 border-2 border-[#767676] rounded-full p-3" @click="prevImage">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#c4c4c4" class="w-5 h-5">
                            <path fill-rule="evenodd" d="M7.72 12.53a.75.75 0 010-1.06l7.5-7.5a.75.75 0 111.06 1.06L9.31 12l6.97 6.97a.75.75 0 11-1.06 1.06l-7.5-7.5z" clip-rule="evenodd" />
                        </svg>
                    </button>                
                    <img class="w-full md:w-auto h-auto md:h-[440px] 2xl:h-[880px] mx-auto object-cover" :src="selectedImage" :alt="`image-${selectedIndex}`">                    
                    <button class="hidden md:flex bg-black hover:bg-[#767676] border-2 border-[#c4c4c4] rounded-full p-3" @click="nextImage">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-5 h-5">
                            <path fill-rule="evenodd" d="M16.28 11.47a.75.75 0 010 1.06l-7.5 7.5a.75.75 0 01-1.06-1.06L14.69 12 7.72 5.03a.75.75 0 011.06-1.06l7.5 7.5z" clip-rule="evenodd" />
                        </svg>
                    </button>     
                    <button class="absolute md:hidden right-0 mr-4 border-2 border-[#767676] rounded-full p-3" @click="nextImage">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#c4c4c4" class="w-5 h-5">
                            <path fill-rule="evenodd" d="M16.28 11.47a.75.75 0 010 1.06l-7.5 7.5a.75.75 0 01-1.06-1.06L14.69 12 7.72 5.03a.75.75 0 011.06-1.06l7.5 7.5z" clip-rule="evenodd" />
                        </svg>
                    </button>                
                </div>                             
            </div>
        </div>
    </div>
</template>

<script setup>
    import rectSrc from "/Rectangle 4.png";

    const btnTitle = "Pesan";
    
    const route = useRoute();
    const id = route.params.id;
    const { data: selectedId } = await useFetch('https://dummyjson.com/products/'+id);

    const { data: anotherProducts} = await useFetch('https://dummyjson.com/products?limit=5&skip=53')

    let formatPrice = (price) => {
        let result = Math.floor(price)
        return result.toLocaleString('id-ID', { useGrouping: true })
    };

    let normalPrice = (price) => {
        let result = price * 14900
        return result
    };

    let afterDiscount = (price, discount) => {
        let result = normalPrice(price) - ( normalPrice(price) * (discount/100))
        return result
    };

    let quantity = ref(parseInt(route.query.quantity) || 1);

    let decrement = () => {
        if(quantity.value > 1){
            quantity.value -= 1;
        }
    }

    let increment = () => {
        quantity.value += 1;
    }

    const showModal = ref(false);

    const openModal = () => {
        showModal.value = true;
        document.body.classList.add('modal-open');
    };    

    const closeModal = () => {
        showModal.value = false;
        document.body.classList.remove('modal-open');
    };

    const showImgViewer = ref(false);
    const selectedIndex = ref(0);
    const selectedImage = ref('');

    const openImgViewer = (index) => {
        showImgViewer.value = true;
        selectedIndex.value = index;
        selectedImage.value = selectedId.value.images[index];
    }

    const closeImgViewer = () => {
        showImgViewer.value = false;
    }

    const prevImage = () => {
        if (selectedIndex.value > 0) {
            selectedIndex.value--;
            selectedImage.value = selectedId.value.images[selectedIndex.value];
        }
    };

    const nextImage = () => {
        if (selectedIndex.value < selectedId.value.images.length - 1) {
            selectedIndex.value++;
            selectedImage.value = selectedId.value.images[selectedIndex.value];
        }
    };

    let pageTitle = selectedId.value.brand+' - '+selectedId.value.title;
    useHead({
        title: pageTitle,
    });

</script>

<style>
    body.modal-open{
        overflow-y: hidden;
    }

    .img-container {
        position: relative;
    }

    .img-container:hover::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.15); /* Ubah nilai alpha (0.5) sesuai keinginan Anda */
        z-index: 1;
    }

    .img-container:hover img {
        opacity: 0.9; /* Ubah nilai opasitas (0.7) sesuai keinginan Anda */        
    }

</style>
