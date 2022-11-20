<script setup>
import Hero from '@/Components/Hero.vue';
import Testimonials from '@/Components/Testimonials.vue';
import Team from '@/Components/Team.vue';
import Feature from '@/Components/Feature.vue';
import Menu from '@/Components/Menu.vue';
import Footer from '@/Components/Footer.vue';
import Navbar from "@/Components/Navbar.vue";
</script>

<template>
    <section>
        <Navbar></Navbar>
        <Hero id="home"></Hero>
        <template v-if="customer">
            <template v-if="formdata">
                <Feature id="feature" :customer="customer" :formdata="formdata"></Feature>
            </template>
            <template v-else>
                <Feature id="feature" :customer="customer"></Feature>
            </template>
        </template>
        <template v-else>
            <template v-if="formdata">
                <Feature id="feature" :formdata="formdata"></Feature>
            </template>
            <template v-else>
                <Feature id="feature"></Feature>
            </template>
        </template>
        <template v-if="customer">
            <Menu id="menu" :customer="customer"></Menu>
        </template>
        <template v-else>
            <Menu id="menu"></Menu>
        </template>
        <Testimonials id="testimoni"></Testimonials>
        <Team id="tentang-kami"></Team>
        <Footer></Footer>
    </section>
</template>
