<template>
    <div>
        <NuxtLayout :name="header"></NuxtLayout>
        <div class="w-[388px] md:w-[1206px] mx-auto my-[88px]">
            <section class="w-full">
                <h1 class="text-[24px] text-[#FF5A5F] text-center font-bold">Koleksi musim panas pria</h1>
                <p class="w-full leading-[18.75px] text-[16px] text-[#484848] text-center font-light mt-2">
                    Tingkatkan gaya Anda di musim panas ini dengan koleksi terbaru kami khusus untuk pria. Hadir dengan pilihan pakaian yang nyaman, trendi, dan tetap terlihat keren di bawah terik matahari. Dari kemeja dengan bahan ringan hingga celana pendek yang stylish, kami memiliki segala yang Anda butuhkan untuk tampil gaya di setiap kesempatan. Jelajahi koleksi musim panas kami sekarang dan hadirkan sentuhan yang segar pada gaya Anda.
                </p>
            </section>
            <section id="categories" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Kategori</h1>
                <div class="grid grid-cols-1 md:grid-cols-3 md:gap-4 mt-6 gap-y-4 md:gap-y-0">
                    <MiniCardHor :to="`#${categories[10]}`" :src="imgMensShirts" :alt="categories[10]" :title="`Pakaian pria`" />                    
                    <MiniCardHor :to="`#${categories[11]}`" :src="imgMensShoes" :alt="categories[11]" :title="`Sepatu pria`" />                    
                    <MiniCardHor :to="`#${categories[12]}`" :src="imgMensWatches" :alt="categories[12]" :title="`Jam tangan pria`" />                    
                </div>                
            </section>
            <section id="secondrow" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Jelajahi Produk-Produk Terkini</h1>
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Jelajahi daftar produk kami dan temukan solusi yang sempurna untuk meningkatkan gaya hidup Anda.</p>
                <div class="relative overflow-hidden mt-6">
                    <div class="absolute z-10 mt-12 md:mt-[65.87px] ml-[104px] md:ml-[503px]">
                        <img class="block w-1/2 md:w-[104.5px] md:h-[112.27px] ml-10 md:ml-9" src="/icons/airbnb-plus.png" alt="">
                        <div class="mt-[37.87px]">
                            <SecondaryCTA :to="`#`" :btnTitle="btnTitle" />
                        </div>
                    </div>
                    <img class="w-full h-[310px] rounded-[4px] object-cover" src="/images/airbnb-plus-1.png" alt="">
                    <div class="absolute inset-0 bg-black opacity-[15%] rounded-[4px]"></div>  
                </div>
            </section>
            <!-- data fetch from api -->
            <section id="mens-shirts" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Pakaian Pria</h1>                
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Jelajahi daftar produk kami dan temukan solusi yang sempurna untuk meningkatkan gaya hidup Anda.</p>
                <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-6">                    
                    <mini-card-ver v-for="m in mensShirts.products" :key="m.id" :to="`/products/${m.id}`" :src="m.thumbnail" :alt="m.title" :country="m.category" :title="'Rp '+formatPrice(m.price * 14900)" :desc="m.title" :rating="m.rating" />                                                               
                </div>   
            </section>
            <section id="mens-shoes" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Sepatu Pria</h1>            
                <div class="grid grid-cols-1 md:grid-cols-4 md:gap-x-4 gap-y-4 md:gap-y-8 mt-[51px]">            
                    <ThreeColsCard v-for="m in mensShoes.products" :key="m.id" :to="`/products/${m.id}`" :src="m.thumbnail" :alt="m.title" :city="m.category" :rating="m.rating" :desc="'Rp '+formatPrice(m.price * 14900)+' - '+m.title" />                    
                </div>
            </section>
            <section id="mens-watches" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Jam tangan Pria</h1>
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Jelajahi daftar produk kami dan temukan solusi yang sempurna untuk meningkatkan gaya hidup Anda.</p>
                <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 mt-6">
                    <mini-card-ver v-for="m in mensWatches.products" :key="m.id" :to="`/products/${m.id}`" :src="m.thumbnail" :alt="m.title" :country="m.category" :title="'Rp '+formatPrice(m.price * 14900)" :desc="m.title" :rating="m.rating" />
                </div>
            </section>
            <!-- <section id="sixthrow" class="mt-[88px]">
                <h1 class="text-[24px] text-[#484848] font-bold">Destinations Airbnb Plus à la Une</h1>
                <p class="w-full md:w-[571px] leading-[18.75px] text-[16px] text-[#484848] font-light mt-2">Voyages de plusieurs jours organisés par des experts locaux avec activités, repas et logements compris</p>
                <div class="grid grid-cols-1 md:grid-cols-3 md:gap-4 mt-6">
                    <FourColsCard v-for="s in sixthrow" :key="s.id" :src="s.src" :alt="s.alt" :plus="s.plus" :desc="s.desc" />                    
                </div>
            </section> -->
        </div>
        <button @click="scrollToTop" id="scrollBtn" class="fixed hidden bottom-16 right-4 bg-[#FF5A5F] hover:bg-[#E55155] rounded-full p-3 shadow">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-6 h-6">
                <path fill-rule="evenodd" d="M11.47 2.47a.75.75 0 011.06 0l7.5 7.5a.75.75 0 11-1.06 1.06l-6.22-6.22V21a.75.75 0 01-1.5 0V4.81l-6.22 6.22a.75.75 0 11-1.06-1.06l7.5-7.5z" clip-rule="evenodd" />
            </svg>
        </button>
    </div>
    <NuxtLayout :name="footer"></NuxtLayout>
</template>

<script setup>
    // const { data: products } = await useFetch('https://fakestoreapi.com/products?limit=6');
    // console.log(products);

    const { data:categories } = await useFetch('https://dummyjson.com/products/categories');
    const imgMensShirts = "https://images.unsplash.com/photo-1603252110481-7ba873bf42ab?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80";
    const imgMensShoes = "https://images.unsplash.com/photo-1621996659546-b0dd8b7e57af?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=464&q=80";
    const imgMensWatches = "https://images.unsplash.com/photo-1619225379807-e9002c44c462?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80";
    const { data:mensShirts } = await useFetch('https://dummyjson.com/products/category/mens-shirts');
    const { data:mensShoes } = await useFetch('https://dummyjson.com/products/category/mens-shoes');
    const { data:mensWatches } = await useFetch('https://dummyjson.com/products/category/mens-watches');

    let formatPrice = (price) => {
        let result = Math.floor(price)
        return result.toLocaleString('id-ID', { useGrouping: true })
    };

    const scrollToTop = () => {
        window.scrollTo({
            top: 0,
            behavior: 'smooth',
        });
    };

    onMounted(() => {
        window.addEventListener('scroll', handleScroll);
    });

    const handleScroll = () => {
        const scrollBtn = document.getElementById('scrollBtn');   
        const scrollPosition = window.pageYOffset || document.documentElement.scrollTop;

        // Jarak scroll sebelum tombol muncul (misalnya 300 piksel)
        const scrollThreshold = 300;

        if (scrollPosition > scrollThreshold) {
            scrollBtn.classList.remove('hidden');
        } else {
            scrollBtn.classList.add('hidden');
        }
    };

    useHead({
        title: "Airbnb"
    });

    const header = "header";
    const footer = "footer";
    const btnTitle = "Jelajahi Sekarang";

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