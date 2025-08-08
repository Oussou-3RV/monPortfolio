<template>
    <section class="text-white mt-20 " id="service">
        <div class="px-4 xl:pl-16">
            <h2 class="text-center text-4xl font-bold text-white mb-4 lg:text-left"> My Services</h2>
        </div>
        <div class="py-8 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3 xl:px-16">
            
            <div v-for="service in services" :key="service.id" data-aos="fade-up"
                class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]">

                <div class="mx-auto w-20 h-24 text-center xl:h-28 xl:w-28">
                    <div>
                        <img :src="service.icon" alt="icon">
                    </div>
                </div>
                <div class="text-center">
                    <h3 class="pt-8 text-xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-tr from-primary to-secondary lg:text-xl">
                        {{ service.name }}
                    </h3>
                    <p class="text-grey pt-4 text-sm group-hover:text-white md:text-base">
                        {{ service.description }}
                    </p>
                </div>
            </div>
        </div>

    </section>
</template>

<script setup>
import { ref } from 'vue';

const services = ref([

    {   
        id:1,
        icon:'https://img.icons8.com/?size=100&id=12447&format=png&color=ffffff',
        name: 'WEB DEVELOPMENT',
        description: 'lorem ipsum dolor sit amer consecutive adisicing elit dicta, utl'
    },
    {   
        id:2,
        icon:'https://img.icons8.com/?size=100&id=TAH7mJxpBhnm&format=png&color=eeffff',
        name: 'Techinical Writing',
        description: 'lorem ipsum dolor sit amer consecutive adisicing elit dicta, utl'
    },
    {   
        id:3,
        icon:'https://img.icons8.com/?size=100&id=K802902EP1kb&format=png&color=ffffff',
        name: 'Mobile DEVELOPMENT',
        description: 'lorem ipsum dolor sit amer consecutive adisicing elit dicta, utl'
    },
    {   
        id:4,
        icon:'https://img.icons8.com/?size=100&id=124385&format=png&color=ffffff',
        name: 'Mailing',
        description: 'lorem ipsum dolor sit amer consecutive adisicing elit dicta, utl'
    },
    {   
        id:5,
        icon:'https://img.icons8.com/?size=100&id=TNMFlPDNS18k&format=png&color=ffffff',
        name: 'graphic disign',
        description: 'lorem ipsum dolor sit amer consecutive adisicing elit dicta, utl'
    },
    {   
        id:6,
        icon:'https://img.icons8.com/?size=100&id=78326&format=png&color=ffffff',
        name: 'WEB disign',
        description: 'lorem ipsum dolor sit amer consecutive adisicing elit dicta, utl'
    },

])

</script>

