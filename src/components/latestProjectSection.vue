<template>
    <section class="text-white mt-20">
        <div class="px-4 xl:pl-16">

            <div class="mb-4 md:flex md:justify-between xl:pr-16">
                <h2 class="text-4xl font-bold text-white">My latest Project</h2>
                <div class="flex space-x-4 mb-4 mt-5 md:mt-5">
                    <button class="hover:text-primary " v-for="category in ['all','web development','Mobile app']"
                        :key="category" @click="() => selectedCategory = category">
                        {{ category }}
                    </button>
                </div>
            </div>

            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3" data-aos="fade-right">
                <div v-for="Project in filterProjects" :key="Project.id">
                    <div class="h-52 md:h-[24rem] rounded-t-xl relative group"
                        :style="{backgroundImage:'url('+Project.image +')',backgroundSize:'cover'}">

                        <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                            hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-5000">

                            <a href='#project' class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link">
                                <i class="fa-solid fa-eye fa-2xl" style="padding: 1.5rem 0.5rem;"></i>
                            </a>
                        </div>
                    </div>  
                    <div class="text-white rounded-b-xl  bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                        <h3 class="text-lg mb-3 font-semibold uppercase lg:text-xl">{{ Project.title }}</h3>
                        <p class="text-[#ADB7BE]">{{ Project.description }}</p>

                        <div class="flex flex-wrap p-2.5">
                            <div v-for="technology in Project.technologies" :key="technology"
                             class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                                style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border:1px solid #111827;" >
                                <p class="px-2 py-2 ">{{ technology }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </ul>
        </div>

    </section>
</template>

<script setup>
import { computed, ref } from 'vue';

const selectedCategory = ref('all')

const filterProjects = computed(()=>{
    if(selectedCategory.value == 'all')
        return Projects.value
    return Projects.value.filter(p => p.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase())
})

const Projects = ref([
    {
        id: 1,
        category: 'Web Development',
        image: 'src/assets/project1.webp',
        title: 'Portfolio Website',
        description: 'Un site portfolio moderne en Vue.js avec Tailwind CSS, présentant mes projets, mon parcours et mes compétences.',
        technologies: ['Vue.js 3', 'Tailwind CSS']
    },
    {
        id: 2,
        category: 'Web Development',
        image: 'src/assets/project2.webp',
        title: 'E-commerce Store',
        description: 'Une boutique en ligne complète avec gestion du panier, paiement en ligne et tableau de bord administrateur.',
        technologies: ['Nuxt.js', 'Express', 'MongoDB']
    },
    {
        id: 3,
        category: 'Mobile App',
        image: 'src/assets/project3.webp',
        title: 'Fitness Tracker',
        description: 'Application mobile pour suivre les séances d’entraînement, l’alimentation et les progrès physiques.',
        technologies: ['Vue Native', 'Firebase']
    },
    {
        id: 4,
        category: 'Web Development',
        image: 'src/assets/project4.png',
        title: 'Blog Platform',
        description: 'Une plateforme de blogging avec authentification, éditeur de texte riche et système de commentaires.',
        technologies: ['Vue.js 3', 'Node.js', 'PostgreSQL']
    },
    {
        id: 5,
        category: 'Desktop App',
        image: 'src/assets/project5.png',
        title: 'Personal Finance Manager',
        description: 'Application de bureau pour gérer ses dépenses, revenus et budgets mensuels.',
        technologies: ['Electron', 'Vue.js', 'SQLite']
    },
    {
        id: 6,
        category: 'Web Development',
        image: 'src/assets/project6.png',
        title: 'Hotel Booking System',
        description: 'Application web pour réserver des chambres d’hôtel, gérer les disponibilités et effectuer des paiements en ligne.',
        technologies: ['Vue.js 3', 'Express', 'MySQL']
    }
]);
</script>

