<template>
    <section class="text-white mt-10" id="skills">
        <div class="absolute right-0 top-[110rem] h-full w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full bg-primary flex blur-2xl">
                </span>
                <span class="w-16 h-32 rounded-l-full flex blur-2xl mt-14"></span>
            </span>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 xl:px-16 ">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">

                <h2 class="text-4xl font-bold text-white text-left mb-4">My
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Skills</span>
                </h2>
                <div class="mt-8" v-for="skill in skills" :key="skill.id">
                    <div class="flec items-end justify-between " data-aos="fade-right">
                        <h4 class="font-semibold uppercase text-white">{{ skill.name }}</h4>
                        <h3 class="text-2xl font-bold text-white">{{ skill.width }}</h3>
                        <div class="mt-2 h-1 w-full bg-[#131d30] rounded-full">
                            <div class="h-1 rounded-full bg-primary" :style="`width:${skill.width}`"></div>
                        </div>
                    </div>
                </div>
            </div>
            <div data-aos="flip-left">
                <h2 class="text-4xl font-bold text-white text-left mb-8 md:text-center md:mt-0 mt-9">My experience</h2>
                <div class="space-y-8 py-8" data-aos="fade-left">
                    <div v-for="element in experiences" :key="element.id"
                        class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]">
                        <div class="w-1/4">
                            <img src="https://img.icons8.com/?size=100&id=ScAViD0I8h4B&format=png&color=ffffff" alt="lawyer">
                        </div>
                        <div class="w-3/4">
                            <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">{{ element.role }}</h3>
                            <p class="text-white">{{ element.company }}</p>
                            <p class="text-white">{{ element.annee }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';

const skills = ref([
    {
        id:1,
        name:'Html & Css',
        width:'85%'
    },
    {
        id:2,
        name:'Java script',
        width:'80%'
    },
    {
        id:3,
        name:'java',
        width:'80%'
    },
    {
        id:4,
        name:'C#',
        width:'75%'
    },
])

const experiences = ref([
    {
        id:1,
        role:'backend dev',
        company:'Microsoft',
        annee:2024
    },
    {
        id:2,
        role:'backend dev',
        company:'Apple',
        annee:'2023'
    }
])
</script>

<style lang="scss" scoped>

</style>