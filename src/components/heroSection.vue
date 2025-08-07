<template>
    <section class="relative w-full" data-aos="zoom-in-up">
        
        <div class="w-full px-5 sm:px-8 md:px-12 lg:px-8 max-w-screen-lg lg:max-w-[85%] mx-auto relative ">
            <div class="grid lg:grid-cols-2 gap-10 xl:gap-15 pt-24 relative">
                <div class="lg:py-6 ">
                    <div class="text-center lg:text-left ">
                        <h1 class="pt-4 text-white font-bold text-5xl lg:text-6xl">
                            Hi, i'm <span class="text-transparent bg-clip-text bg-gradient-to-tr from-primary to-pink-500">Ousmane</span> 😎
                        </h1>
                    </div>
                    <p class="text-gray-300 pt-8 text-center lg:text-left ">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit i dont know.
                         Minus odit quod blanditiis corporis officia asperiores je rajoute du texte.
                        Voluptatem cum modi, incidunt doloribus sit at quis nulla eaque je ne sais pourquoi ??.
                    </p>
                    <div class="flex flex-col gap-3 pt-9 md:flex-row md:w-full max-lg:justify-center ">
                        <!-- Bouton Hire Me -->
                        <button
                            class="bg-primary px-6 md:px-7 py-4 rounded-full relative group w-full md:w-max flex justify-center transition-all duration-300 hover:bg-primary/80 hover:-translate-y-1">
                            <span class="flex items-center justify-center text-white">Hire Me</span>
                        </button>

                        <!-- Bouton Download -->
                        <button
                            class="border border-primary px-6 md:px-7 py-4 rounded-full relative group w-full md:w-max flex justify-center transition-all duration-300 hover:bg-primary hover:-translate-y-1">
                            <div class="flex items-center gap-2">
                                <i class="fa-solid fa-download" style="color: white;"></i>
                                <a href="/resume.pdf" download="resume.pdf"
                                    class="text-primary transition-colors duration-300 group-hover:text-white">Resume</a>
                            </div>
                        </button>
                    </div>
                </div>
                <div class="md:flex lg:h-full ">
                    <div class="flex w-full min-h-96 lg:min-h-[none] lg:w-full lg:h-full justify-center relative">
                        <div></div>
                        <div class="absolute h-full z-10 p-2 -translate-y-1/2 top-1/2 rounded-full shadow-lg border border-primary    ">
                            <img src="/src/assets/dev.webp" alt="photo de moi" width="500" height="auto" loading="lazy"
                            class="w-full h-full rounded-full object-cover">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import AOS from 'aos';
import 'aos/dist/aos.css'
AOS.init();
</script>