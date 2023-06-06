<template>
    <div>
        <div class="flex flex-col">
            <div>
                <ProductsNavbar />    
            </div>        
            <div class="mt-[58px] md:mt-[65px]">
                <CategoryTabs />
            </div>
        </div>
        <div class="w-full mb-[88px]">
            <div class="w-[388px] md:w-[1206px] mx-auto py-6">
                <section :id="categories[0]" class="mt-[160px] md:mt-[120px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Ponsel Pintar</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in smartphones.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[1]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Komputer Jinjing</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in laptops.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[2]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Parfum</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in fragrances.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[3]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Perawatan Kulit</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in skincare.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[4]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Bahan Makanan</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in groceries.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[5]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Dekorasi Rumah</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in homeDecoration.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[6]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Perabotan Rumah</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in furniture.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[19]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Lampu</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in lighting.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[7]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Atasan</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in tops.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[8]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Pakaian Wanita</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in womensDresses.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[9]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Sepatu Wanita</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in womensShoes.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[13]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Jam Tangan Wanita</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in womensWatches.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[14]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Tas Wanita</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in womensBags.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[15]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Perhiasan Wanita</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in womensJewellery.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[10]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Pakaian Pria</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in mensShirts.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[11]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Sepatu Pria</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in mensShoes.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[12]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Jam Tangan Pria</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in mensWatches.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[16]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Kacamata</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in sunglasses.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[17]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Aksesoris Otomotif</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in automotive.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>
                <section :id="categories[18]" class="mt-[88px]">
                    <h1 class="text-[24px] text-[#484848] font-bold">Motor Dan Aksesoris</h1>                                    
                    <div class="grid grid-cols-2 md:grid-cols-5 md:gap-4 gap-y-4 md:gap-y-0 mt-2">                    
                        <mini-card-ver v-for="i in motorcycle.products" :key="i.id" :to="`/products/${i.id}`" :src="i.thumbnail" :alt="i.title" :country="i.category" :title="'Rp '+formatPrice(i.price * 14900)" :desc="i.title" :rating="i.rating" />                                                               
                    </div>   
                </section>            
            </div>
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
        <button @click="scrollToTop" id="scrollBtn" class="fixed hidden bottom-16 right-4 bg-[#FF5A5F] hover:bg-[#E55155] rounded-full p-3 shadow">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#FFFFFF" class="w-6 h-6">
                <path fill-rule="evenodd" d="M11.47 2.47a.75.75 0 011.06 0l7.5 7.5a.75.75 0 11-1.06 1.06l-6.22-6.22V21a.75.75 0 01-1.5 0V4.81l-6.22 6.22a.75.75 0 11-1.06-1.06l7.5-7.5z" clip-rule="evenodd" />
            </svg>
        </button>
    </div>
</template>

<script setup>
    const { data: categories } = await useFetch('https://dummyjson.com/products/categories');
    const { data:smartphones } = await useFetch('https://dummyjson.com/products/category/smartphones');
    const { data:laptops } = await useFetch('https://dummyjson.com/products/category/laptops');
    const { data:fragrances } = await useFetch('https://dummyjson.com/products/category/fragrances');
    const { data:skincare } = await useFetch('https://dummyjson.com/products/category/skincare');
    const { data:groceries } = await useFetch('https://dummyjson.com/products/category/groceries');
    const { data:homeDecoration } = await useFetch('https://dummyjson.com/products/category/home-decoration');
    const { data:furniture } = await useFetch('https://dummyjson.com/products/category/furniture');
    const { data:tops } = await useFetch('https://dummyjson.com/products/category/tops');
    const { data:womensDresses } = await useFetch('https://dummyjson.com/products/category/womens-dresses');
    const { data:womensShoes } = await useFetch('https://dummyjson.com/products/category/womens-shoes');
    const { data:womensWatches } = await useFetch('https://dummyjson.com/products/category/womens-watches');
    const { data:womensBags } = await useFetch('https://dummyjson.com/products/category/womens-bags');
    const { data:womensJewellery } = await useFetch('https://dummyjson.com/products/category/womens-jewellery');
    const { data:sunglasses } = await useFetch('https://dummyjson.com/products/category/sunglasses');
    const { data:automotive } = await useFetch('https://dummyjson.com/products/category/automotive');
    const { data:motorcycle } = await useFetch('https://dummyjson.com/products/category/motorcycle');
    const { data:lighting } = await useFetch('https://dummyjson.com/products/category/lighting');
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
        title: "Produk - Airbnb"
    })
</script>