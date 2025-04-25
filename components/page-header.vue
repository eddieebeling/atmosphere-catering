<template>
    <div class="page-header">
        <nav class="page-header__nav">
            <a v-for="(item, index) in leftNavLinks" :key="index" @click="scrollTo(item.anchor)"
                class="page-header__link">{{ item.text }}</a>
        </nav>
        <img :src="logoUrl" :alt="title" @click="scrollToTop" class="page-header__logo" />
        <nav class="page-header__nav">
            <a v-for="(item, index) in rightNavLinks" :href="item.url" :key="index" @click="scrollTo(item.anchor)"
                class="page-header__link">{{ item.text }}</a>
        </nav>
    </div>
</template>

<script setup>
const title = ref("Atmosphere Catering");
const logoUrl = ref(
    "https://res.cloudinary.com/eddieebeling/image/upload/v1745462447/atmo-logo_gtp2tr.jpg",
);
const scrollTo = (section) => {
    const element = document.getElementById(section);
    if (element) {
        element.scrollIntoView({ behavior: "smooth" });
    }
};

const scrollToTop = () => {
    window.scrollTo({ top: 0, behavior: "smooth" });
};

const leftNavLinks = ref([
    { text: "Catering", anchor: "catering" },
    { text: "Parties", anchor: "parties" },
    { text: "Events", anchor: "events" },
]);
const rightNavLinks = ref([
    { text: "Testimonials", anchor: "testimonials" },
    { text: "Menus", anchor: "menus" },
    { text: "Contact", anchor: "contact" },
]);
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;

.page-header {
    display: flex;
    justify-content: center;
    align-items: center;

    &__logo {
        width: 130px;
        height: auto;
        margin: 1.5rem;
        padding: .5rem;
        cursor: pointer;
    }

    &__nav {
        display: none;

        @media (min-width: $sm) {
            display: flex;
            justify-content: center;
            align-items: center;
        }
    }

    &__link {
        color: rgba(255, 255, 255, 0.65);
        text-decoration: none;
        font-size: 1rem;
        margin: 0 1rem;
        transition: color 0.3s ease;
        text-transform: uppercase;
        cursor: pointer;

        &:hover {
            color: rgba(255, 255, 255, 1);
        }

        @media (min-width: $md) {
            margin: 0 2rem;
        }
    }
}
</style>