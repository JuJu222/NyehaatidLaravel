<template>
    <!-- for vue instead of using a href, vue router links will be used -->
    <!-- replace appropriate tags after installing vue-router -->
    <section>
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

<script>
import Menu from './Menu.vue'
import Hero from "./Hero.vue";
import Team from "./Team";
import Footer from "./Footer";
import Feature from "./Feature";
import Testimonials from "./Testimonials";

export default {
    name: "Home",
    components: {
        Feature,
        Menu,
        Hero,
        Team,
        Footer,
        Testimonials
    },
    props: ['customer', 'formdata'],
    methods: {
        MenuHandler(flag) {
            if (flag) {
                document.getElementById("list").classList.add("top-100");
                document.getElementById("list").classList.remove("hidden");
                document.getElementById("close").classList.remove("hidden");
                document.getElementById("open").classList.add("hidden");
            } else {
                document.getElementById("list").classList.remove("top-100");
                document.getElementById("list").classList.add("hidden");
                document.getElementById("close").classList.add("hidden");
                document.getElementById("open").classList.remove("hidden");
            }
        },
    },
};
</script>

<style scoped>
/* Top menu */
.top-100 {
    animation: slideDown 0.5s ease-in-out;
}
@keyframes slideDown {
    0% {
        top: -50%;
    }
    100% {
        top: 0;
    }
}
* {
    outline: none !important;
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    -webkit-tap-highlight-color: transparent;
}
</style>
