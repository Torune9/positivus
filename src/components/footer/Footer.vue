<template>
    <section class="mt-42">
        <div class="text-white bg-slate-950 rounded-tl-4xl rounded-tr-4xl p-10">
            <div class="flex flex-row justify-between">
                <div class="flex flex-row gap-x-2 items-center">
                    <div>
                        <img :src="icon" alt="icon" class="h-5 invert-100">
                    </div>
                    <div>
                        <img :src="positivus" alt="positivus-icon" class="h-5 invert-100">
                    </div>
                </div>
                <ul >
                    <router-link class="flex flex-row gap-x-5 items-center h-full">
                        <li v-for="(menu, i) in menus" class="p-2 rounded-md px-4 text-sm underline cursor-pointer"
                            :class="i == menus.length - 1 ? 'border' : ''">
                            {{ menu.name }}
                        </li>
                    </router-link>
                </ul>
                <ul class="flex flex-row justify-evenly items-center  w-42">
                    <li v-for="icon in icons"
                        class="h-8 w-8 border rounded-full flex items-center justify-center bg-white text-slate-950 cursor-pointer">
                        <font-awesome-icon :icon="icon.name" size="lg" />
                    </li>
                </ul>

            </div>
            <div class="grid grid-cols-2 border-b py-20">
                <div class="flex flex-col gap-5">
                    <h1 class="bg-lime-300 w-fit text-slate-950 font-semibold rounded-md px-2">Contact Us</h1>
                    <p>Email : info@positivus.com</p>
                    <p>Phone : 555-567-8901</p>
                    <div>
                        <p>Address : 123 Main st</p>
                        <p>Moonstone City,Stardust State 12345</p>
                    </div>
                </div>
                <form action="#" class="bg-white/10 rounded-2xl px-10 flex items-center gap-x-4">
                    <input type="text" class="border h-12 rounded-xl pl-4" placeholder="Email">
                    <button
                        class="bg-lime-300 text-slate-950 w-full h-12 rounded-xl hover:bg-lime-200 cursor-pointer transition-colors duration-300">
                        Subcsribe to news
                    </button>
                </form>
            </div>
            <div class="flex gap-x-14 mt-10">
                <span>&copy; 2025 Positivus. All Rights Reserved.</span>
                <router-link class="underline" to="#">Privacy Policy</router-link>
            </div>
        </div>
    </section>
</template>

<script setup>
import icon from '@/assets/images/Icon.png'
import positivus from '@/assets/images/Positivus.png'

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
const icons = [
    {
        name: "fa-brands fa-linkedin"
    },
    {
        name: "fa-brands fa-facebook"
    },
    {
        name: "fa-brands fa-twitter"
    },
]
</script>