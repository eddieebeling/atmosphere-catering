<template>
    <div class="atmosphere-catering__header animate__animated animate__fadeIn">
        <nav class="atmosphere-catering__nav">
            <a v-for="(item, index) in leftNavLinks" :href="item.url" :key="index" class="atmosphere-catering__link">{{ item.text }}</a>
        </nav>
      <img :src="logoUrl" :alt="title" class="atmosphere-catering__logo" />
      <nav class="atmosphere-catering__nav">
        <a v-for="(item, index) in rightNavLinks" :href="item.url" :key="index" class="atmosphere-catering__link">{{ item.text }}</a>
      </nav>
    </div>
</template>

<script setup lang="js">
import { ref } from 'vue'

const title = ref('Atmosphere Catering')
const logoUrl = ref('https://res.cloudinary.com/eddieebeling/image/upload/v1744216763/481854231_1419578952337847_6277475041924269601_n_putmyv.jpg');

const leftNavLinks = ref([
  { text: 'Catering', url: 'https://www.google.com/' },
  { text: 'Events', url: 'https://www.google.com/' },
  { text: 'Parties', url: 'https://www.google.com/' }
]);
const rightNavLinks = ref([
  { text: 'Menus', url: 'https://www.google.com/' },
  { text: 'Pricing', url: 'https://www.google.com/' },
  { text: 'Contact', url: 'https://www.google.com/' }
]);
</script>

<style lang="scss">
@import url("animate.css");
.atmosphere-catering {
    font-family: "Roboto", sans-serif;
    &__header {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    &__logo {
        width: 130px;
        height: auto;
        margin: 1.5rem 3rem;
    }
    &__title {
        font-size: 2rem;
        text-align: center;
    }
    &__nav {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    &__link {
        color: rgba(255, 255, 255, 0.65);
        text-decoration: none;
        font-size: .9375rem;
        margin: 0 1.5rem;
        transition: color 0.3s ease;
        text-transform: uppercase;
        &:hover {
            color: rgba(255, 255, 255, 1);
        }
    }
}
</style>