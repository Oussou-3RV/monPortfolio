<template>
    <header class="flex justify-between items-center p-6 bg-opacity-50 z-20">
        <div class="text-white text-3xl font-bold">LOGO</div>

        <!-- Mobile Toggle Button -->
        <div class="md:hidden z-30">
            <button type="button" class="block focus:outline-none " @click="isMenuOpen = !isMenuOpen">
                <span v-if="isMenuOpen" class="text-5xl close">
                    <i class="fa-solid fa-xmark" style="color: #fafafa; font-size: 2.3rem;"></i>
                </span>
                <span v-else class="text-5xl menu">
                    <i class="fa-solid fa-bars" style="color: #fafafa; font-size: 2.3rem;"></i>
                </span>
            </button>
        </div>

        <!-- Nav-bar link -->
        <nav :class="['fixed inset-0 z-20 flex flex-col items-center justify-center bg-[#111827] md:relative md:bg-transparent md:flex md:flex-row md:justify-between',
            isMenuOpen ? 'block' : 'hidden']">
            <ul class="flex flex-col items-center space-y-5 md:flex-row md:space-x-5 md:space-y-0">
                <li v-for="item in Menu" :key="item.name" @click="scrollToSection(item.href)">
                    <a :href="item.href"
                        class="block text-white transition hover:text-primary ease-linear text-2xl md:text-lg">
                        {{ item.name }}
                    </a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script setup>
import { ref } from 'vue';

const Menu = ref([
    { name: 'services', href: '#services' },
    { name: 'About Me', href: '#about' },
    { name: 'Skills', href: '#skills' },
    { name: 'Projects', href: '#projects' },
    { name: 'Testimonials', href: '#testimonials' },
    { name: 'Contact', href: '#contact' },
])

const isMenuOpen = ref(false)

const scrollToSection = (href) => {
    isMenuOpen.value = false
    const section = document.querySelector(href)
    if (section) {
        section.scrollIntoView({ bahavior: 'smooth' });
    }
}
</script>