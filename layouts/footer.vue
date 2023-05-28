<template>
    <footer class="invisible fixed bottom-0 left-0 z-20 w-full border-t bg-white px-4 md:px-20 py-3">
        <div class="flex flex-row justify-between items-center">
            <div class="leading-[18.75px] text-[16px] text-[#484848] font-light">
                <span>&copy; 2023 Airbnb, Inc.</span>
            </div>
            <div></div>
        </div>
    </footer>
</template>

<script setup>
    import {ref, onMounted, onBeforeUnmount} from 'vue';

    const footer = ref(null);
    const navBrandSrc = ref('/icons/airbnb-nav.png');

    const onScroll = () => {
        if (document.documentElement.scrollTop > 60 || document.body.scrollTop > 60) {
            footer.value.classList.add('visible');
            footer.value.classList.remove('invisible');            
        } else {
            footer.value.classList.remove('visible');
            footer.value.classList.add('invisible');
        }
    };

    onMounted(() => {
        footer.value = document.querySelector('footer');
        window.addEventListener('scroll', onScroll);
    });

    onBeforeUnmount(() => {
        window.removeEventListener('scroll', onScroll);
    });
</script>