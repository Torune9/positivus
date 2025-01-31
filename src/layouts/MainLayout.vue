<template>
    <div>
        <header>
            <NavBar></NavBar>
        </header>
        <main class="mt-14 px-20">
            <slot name="content"/>
        </main>
        <footer class="px-20">
            <FooterSection/>
        </footer>
    </div>
</template>

<script setup>
import FooterSection from '@/components/footer/Footer.vue';
import NavBar from '@/components/navigation/NavBar.vue';
</script>