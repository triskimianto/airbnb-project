<template>
    <div>
        <NuxtLayout :name="header"></NuxtLayout>
        <div class="w-[388px] md:w-[1206px] mx-auto my-[88px]">
            <section id="categories">
                <h1 class="text-[24px] text-[#484848] font-bold">Explorer Airbnb</h1>
                <div class="grid grid-cols-1 md:grid-cols-3 md:gap-4 mt-6 gap-y-4 md:gap-y-0">
                    <MiniCardHor v-for="f in firstrow" :key="f.id" :to="f.to" :src="f.src" :alt="f.alt" :title="f.title" />                    
                </div>                
            </section>
            <section id="secondrow" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Hébergements Airbnb Plus</h1>
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Une sélection de logements vérifiés selon des critères de qualité et de design</p>
                <div class="relative overflow-hidden mt-6">
                    <div class="absolute z-10 mt-12 md:mt-[65.87px] ml-20 md:ml-[503px]">
                        <img class="block w-1/2 md:w-[104.5px] md:h-[112.27px] ml-12 md:ml-[47.66px]" src="/icons/airbnb-plus.png" alt="">
                        <div class="mt-[37.87px]">
                            <SecondaryCTA :btnTitle="btnTitle" />
                        </div>
                    </div>
                    <img class="w-full h-[310px] rounded-[4px] object-cover" src="/images/airbnb-plus-1.png" alt="">
                    <div class="absolute inset-0 bg-black opacity-[15%] rounded-[4px]"></div>  
                </div>
            </section>
            <!-- data fetch from api -->
            <section id="products" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Products</h1>                
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Jelajahi daftar produk kami dan temukan solusi yang sempurna untuk meningkatkan gaya hidup Anda.</p>
                <div class="grid grid-cols-1 md:grid-cols-6 md:gap-4 gap-y-4 md:gap-y-0 mt-6">                    
                    <mini-card-ver v-for="p in products" :key="p.id" :to="`/products/${p.id}`" :src="p.image" :alt="p.title" :country="p.category" :title="'USD '+p.price" :desc="p.title" :rating="p.rating.rate" />                                                               
                </div>        
            </section>
            <section id="houses" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Découvrez les aventures Airbnb</h1>
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Voyages de plusieurs jours organisés par des experts locaux avec activités, repas et logements compris</p>
                <div class="grid grid-cols-1 md:grid-cols-6 md:gap-4 gap-y-4 md:gap-y-0 mt-6">                    
                    <mini-card-ver v-for="r in houses" :key="r.id" :to="`/rooms/${r.id}`" :src="r.src" :alt="r.alt" :country="r.country" :title="r.title" :desc="r.desc" :rating="r.rating" />                                           
                </div>
            </section>
            <section id="experiences" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Logements dans le monde entier</h1>            
                <div class="grid grid-cols-1 md:grid-cols-4 md:gap-x-4 gap-y-4 md:gap-y-8 mt-[51px]">            
                    <ThreeColsCard v-for="r in experiences" :key="r.id" :to="`/rooms/${r.id}`" :src="r.src" :alt="r.alt" :city="r.city" :rating="r.rating" :desc="r.desc" />                    
                </div>
            </section>
            <section id="adventures" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Expériences très bien notées</h1>
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Voyages de plusieurs jours organisés par des experts locaux avec activités, repas et logements compris</p>
                <div class="grid grid-cols-1 md:grid-cols-6 md:gap-4 mt-6">
                    <mini-card-ver v-for="r in adventures" :key="r.id" :to="`/rooms/${r.id}`" :src="r.src" :alt="r.alt" :country="r.country" :title="r.title" :desc="r.desc" :rating="r.rating" />
                </div>
            </section>
            <section id="sixthrow" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Destinations Airbnb Plus à la Une</h1>
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Voyages de plusieurs jours organisés par des experts locaux avec activités, repas et logements compris</p>
                <div class="grid grid-cols-1 md:grid-cols-3 md:gap-4 mt-6">
                    <FourColsCard v-for="s in sixthrow" :key="s.id" :src="s.src" :alt="s.alt" :plus="s.plus" :desc="s.desc" />                    
                </div>
            </section>
        </div>
    </div>
    <NuxtLayout :name="footer"></NuxtLayout>
</template>

<script setup>
    const { data: products } = await useFetch('https://fakestoreapi.com/products?limit=6');
    console.log(products);

    useHead({
        title: "Airbnb"
    });

    const header = "header";
    const footer = "footer";
    const btnTitle = "Découvrir des logements";

    let firstrow = [
        {
            id: 1,
            to: "#houses",
            src: "/images/cat-1.png",
            alt: "Houses",
            title: "Houses",
        },
        {
            id: 2,
            to: "#experiences",
            src: "/images/cat-2.png",
            alt: "Experiences",
            title: "Experiences",
        },
        {
            id: 3,
            to: "#adventures",
            src: "/images/cat-3.png",
            alt: "Adventures",
            title: "Adventures",
        }
    ];

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

    const houses = rooms.filter((r) => r.category.toLowerCase() == "houses");
    const experiences = rooms.filter((r) => r.category.toLowerCase() == "experiences");
    const adventures = rooms.filter((r) => r.category.toLowerCase() == "adventures");

    let sixthrow = [
        {
            id: 1,
            src: "/images/destinations-1.png",
            alt: "À partir de 577€/personne - 3 jours",
            plus: "Plus de 200 séjours vérifiés",
            desc: "À partir de 577€/personne - 3 jours",
        },
        {
            id: 2,
            src: "/images/destinations-2.png",
            alt: "À partir de 577€/personne - 3 jours",
            plus: "Plus de 200 séjours vérifiés",
            desc: "À partir de 577€/personne - 3 jours",
        },{
            id: 3,
            src: "/images/destinations-3.png",
            alt: "À partir de 577€/personne - 3 jours",
            plus: "Plus de 200 séjours vérifiés",
            desc: "À partir de 577€/personne - 3 jours",
        },
    ];
</script>