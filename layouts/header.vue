<template>
    <div>
        <!-- navbar -->        
        <Navbar />
    
        <div id="hero" class="top-content mb-8">
            <img class="w-full bg-cover" src="/images/hero-bg.png" alt="">
            <div class="md:absolute md:max-w-[391px] max-h-[588px] bg-white rounded-[4px] md:top-[132px] md:left-[73px] 2xl:top-[264px] 2xl:left-[350px] px-4 md:px-6 py-2 md:py-8">
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
                    <MainCTA :btnTitle="btnTitle" />
                </div>                
            </div>
        </div>
    </div>
</template>

<script setup>
    // data
    const btnTitle = "Rechercher";
</script>