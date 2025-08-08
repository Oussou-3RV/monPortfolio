<template>
    <section class="text-white mt-18 " id="about">

        <div class="absolute z-0 top-[93rem] inset-x-0 h-64 flex items-start sm:fixed">
            <div class="h-24 w-64 bg-gradient-to-tr from-primary via-secondary to-[#570cac] blur-2xl opacity-20"></div>
        </div>

        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 sm:py-16 xl:px-16 z-1">
            <div data-aos="flip-right">
                <h2 class="text-4xl font-bold text-white text-left mb-8">My Education</h2>

                <div class="space-y-8 py-8">

                    <div v-for="element in education" :key="element.id"
                        class="flex items-center bg-[#111a3e] rounded-xl">
                        <div class="w-1/4 pl-2">
                            <img src="https://img.icons8.com/?size=100&id=TwX7XgsmjVhu&format=png&color=ffffff"
                                alt="Graduation cap">
                        </div>
                        <div class="w-3/4 pl-4">
                            <a :href=element.link target="_blank"
                                class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                                {{ element.school }}</a>
                            <p class="text-white">{{ element.program }}</p>
                            <p class="text-white">{{ element.year }}</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full " data-aos="flip-left">
                <h2 class="text-4xl font-bold text-white md:text-center text-left mb-4">More about
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Me</span>
                </h2>
                <p class="text-base lg:text-lg mt-4 py-8">Lorem ipsum dolor sit amet consectetur adipisicing elit. A,
                    consectetur iusto! Animi quia ipsa ea quisquam quae, deleniti minima id tenetur officiis, labore
                    exercitationem vel aliquid. Repellat facere velit accusantium?</p>

                <div class="grid grid-cols-3 gap-3 max-w-lg pt-8">
                    <div class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3">
                        <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">
                                +<NumberCount :value="100" :duration="4000" />
                            </h3>
                            <p class="text-sm sm:text-base text-gray-300">Happy Client</p>
                    </div>
                    <div class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3">
                        <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">
                                +<NumberCount :value="150" :duration="4000" />
                            </h3>
                            <p class="text-sm sm:text-base text-gray-300">Project</p>
                    </div>
                    <div class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3">
                        <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">
                                +<NumberCount :value="4" :duration="4000" />
                            </h3>
                            <p class="text-sm sm:text-base text-gray-300">Years experience</p>
                    </div>
                </div>
            </div>

        </div>


    </section>
</template>

<script setup>
import { ref, defineAsyncComponent } from 'vue';

const education = ref([
    {
        id: 1,
        school: 'UQTR',
        program: 'Software Developer',
        year: 'en cours ....',
        link: 'https://www.uqtr.ca/index.shtml'
    },
    {
        id: 2,
        school: 'VINCI',
        program: 'Web Developer',
        year: '2021-2023',
        link: 'https://www.laformation.ma/vinci'
    }
])

const NumberCount = defineAsyncComponent(() => import('@/components/NumberCount.vue'))
</script>
