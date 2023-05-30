<template>
    <div>
        <!-- navbar -->        
        <nav class="parallax fixed flex flex-row justify-between items-center w-full px-6 py-4 z-10 text-white">
            <img class="w-[28.65px] h-[30.73px]" :src="navBrandSrc" alt="nav-brand">
            <div class="hidden md:flex item-center space-x-6">
                <NuxtLink to="/" class="hover:text-[#FF5A5F]">Français (FR)</NuxtLink>
                <NuxtLink to="/" class="hover:text-[#FF5A5F]">EUR €</NuxtLink>
                <NuxtLink to="/" class="hover:text-[#FF5A5F]">Devenir hôte</NuxtLink>
                <NuxtLink to="/" class="hover:text-[#FF5A5F]">Créer son expérience</NuxtLink>
                <NuxtLink to="/" class="hover:text-[#FF5A5F]">Aide</NuxtLink>
                <NuxtLink to="/" class="hover:text-[#FF5A5F]">Inscription</NuxtLink>
                <NuxtLink to="/" class="hover:text-[#FF5A5F]">Connexion</NuxtLink>
            </div>
            <div class="md:hidden">
                <button @click="toggleMobileMenu" class="block focus:outline-none">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                </button>
                <div v-if="isMobileMenuOpen" class="absolute mt-[18px] left-0 w-full bg-white text-[#484848] border-t shadow">
                    <div class="flex flex-col space-y-4 p-4">
                        <NuxtLink to="/">Français (FR)</NuxtLink>
                        <NuxtLink to="/">EUR €</NuxtLink>
                        <NuxtLink to="/">Devenir hôte</NuxtLink>
                        <NuxtLink to="/">Créer son expérience</NuxtLink>
                        <NuxtLink to="/">Aide</NuxtLink>
                        <NuxtLink to="/">Inscription</NuxtLink>
                        <NuxtLink to="/">Connexion</NuxtLink>
                    </div>
                </div>
            </div>                        
        </nav>        
    
        <div id="hero" class="top-content mb-8">
            <img class="w-full bg-cover" src="/images/hero-bg.png" alt="">
            <div class="md:absolute md:max-w-[391px] max-h-[588px] bg-white rounded-[4px] md:top-[132px] md:left-[80px] px-4 md:px-6 py-2 md:py-8">
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
    import {ref, onMounted, onBeforeUnmount} from 'vue';

    const nav = ref(null);
    const navBrandSrc = ref('/icons/airbnb-nav.png');
    const isMobileMenuOpen = ref(false);

    const onScroll = () => {
        if (document.documentElement.scrollTop > 60 || document.body.scrollTop > 60) {
            nav.value.classList.add('bg-white', 'items-center', 'shadow');
            nav.value.classList.remove('text-white');
            navBrandSrc.value = '/icons/airbnb-nav-red.png';
        } else {
            nav.value.classList.remove('bg-white', 'items-center', 'shadow');
            nav.value.classList.add('text-white');
            navBrandSrc.value = '/icons/airbnb-nav.png';
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

    // data
    const btnTitle = "Rechercher";
</script>