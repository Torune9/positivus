<template>
    <!-- Navbar -->
    <section class="h-[68px] flex flex-row justify-around">
        <div class="flex flex-row gap-x-2 items-center">
            <div>
                <img :src="icon" alt="icon" class="h-5">
            </div>
            <div>
                <img :src="positivus" alt="positivus-icon"  class="h-5">
            </div>
        </div>
        <div>
            <ul class="flex flex-row gap-x-10 items-center h-full">
                <li v-for="(menu, i) in menus" class="p-2  px-4 cursor-pointer hover:border-b"  :class="i == menus.length - 1 ? 'border rounded-md hover:bg-lime-300 hover:text-white transition-colors duration-300' : ''">
                    {{ menu.name }}
                </li>
            </ul>
        </div>
    </section>

    <!-- Landing Page -->
    <section class="flex flex-row justify-around gap-x-10 mt-12">
        <div class="flex flex-col justify-between h-80">
            <h1 class="text-6xl">Navigating the <br> digital landscape <br> for success</h1>
            <button class="w-52 p-2 rounded-md bg-slate-900 text-white hover:cursor-pointer hover:bg-slate-700 transition-colors duration-300 ease">
                Book a consultation
            </button>
        </div>
        <div>
            <img :src="illustration" alt="illustration" width="500">
        </div>
    </section>

    <section class="mt-12 border-slate-500">
        <div>
            <img :src="logoType" alt="logo-brand">
        </div>
    </section>
</template>

<script setup>
import icon from '@/assets/images/Icon.png'
import illustration from '@/assets/images/Illustration.png'
import positivus from '@/assets/images/Positivus.png'
import logoType from '@/assets/images/Logotypes.png'
const menus = [
    {
        name: 'About Us'
    },
    {
        name: 'Services'
    },
    {
        name: 'Use Cases'
    },
    {
        name: 'Pricing'
    },
    {
        name: 'Blog'
    },
    {
        name: 'Request a quote'
    },
]
</script>