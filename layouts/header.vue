<template>
    <div>
        <!-- navbar -->        
        <Navbar />
    
        <div id="hero" class="top-content mb-8">
            <div class="w-full h-screen md:h-full">
                <!-- Photo by <a href="https://unsplash.com/@tphocus?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Trinity Treft</a> on <a href="https://unsplash.com/photos/pSZJ0w_ecrA?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a> -->
                <img class="w-full h-full object-cover object-center" src="/images/hero-bg-2.png" alt="Photo by Trinity Treft on Unsplash">
            </div>
            <div class="absolute inset-0 flex items-center">
                <div class="mx-auto max-w-[391px] md:max-w-[490px] max-h-[588px] p-8">
                    <h1 class="text-white text-[36px] md:text-[48px] font-bold leading-10 md:leading-[52px] text-stroke">Embrace the Sun, Unleash Your <span class="text-[#FF5A5F]">Style!</span></h1>
                </div>                
            </div>
            <!-- <div class="md:absolute md:max-w-[391px] max-h-[588px] bg-white rounded-[4px] md:top-[132px] md:left-[73px] 2xl:top-[264px] 2xl:left-[350px] px-4 md:px-6 py-2 md:py-8">
                <h1 class="text-[32px] font-medium leading-[38px]">Réservez des hébergements et des activités uniques.</h1>
                <div class="w-full mt-6">
                    <label class="text-[12px] text-[#484848] font-bold uppercase" for="Où">
                        Où
                    </label>
                    <input type="text" class="w-full h-[48px] border rounded-[2px] text-[#484848] placeholder-[#8F8F8F] text-[16px] font-normal mt-2 px-4 py-4" placeholder="Partout">
                </div>
                <div class="flex flex-row w-full mt-4">
                    <div>
                        <label class="text-[12px] text-[#484848] font-bold uppercase" for="Arrivée">
                            Arrivée
                        </label>
                        <input type="date" class="w-full h-[48px] border rounded-l-[2px] text-[#484848] placeholder-[#8F8F8F] text-[16px] font-normal mt-2 px-4 py-4" placeholder="Arrivée">
                    </div>
                    <div>
                        <label class="text-[12px] text-[#484848] font-bold uppercase" for="Départ">
                            Départ
                        </label>
                        <input type="date" class="w-full h-[48px] border rounded-r-[2px] text-[#484848] placeholder-[#8F8F8F] text-[16px] font-normal mt-2 px-4 py-4 " placeholder="Départ">
                    </div>
                </div>
                <div class="w-full mt-4">
                    <label class="text-[12px] text-[#484848] font-bold uppercase" for="Voyageurs">
                        Voyageurs
                    </label>
                    <input type="text" class="w-full h-[48px] border rounded-[2px] text-[#484848] placeholder-[#8F8F8F] text-[16px] font-normal mt-2 px-4 py-4" placeholder="Voyageurs">
                </div>
                <div class="float-right mt-6">
                    <div class="w-[146px]">
                        <MainCTA :btnTitle="btnTitle" />
                    </div>                    
                </div>                
            </div> -->
        </div>
    </div>
</template>

<script setup>
    // data
    const btnTitle = "Rechercher";
</script>

<style>
    .text-stroke {  
        -webkit-text-stroke-width: 1px;
        -webkit-text-stroke-color: #FF5A5F;
    }
</style>