<template>
    <div class="atmosphere-catering__header animate__animated animate__fadeIn">
        <nav class="atmosphere-catering__nav">
            <a href="https://www.google.com/" class="atmosphere-catering__link">Catering</a>
            <a href="https://www.google.com/" class="atmosphere-catering__link">Events</a>
            <a href="https://www.google.com/" class="atmosphere-catering__link">Parties</a>
        </nav>
      <img src="../../../atmosphere-logo.jpg" alt="Atomosphere Catering" class="atmosphere-catering__logo" />
      <nav class="atmosphere-catering__nav">
        <a href="https://www.google.com/" class="atmosphere-catering__link">Menus</a>
        <a href="https://www.google.com/" class="atmosphere-catering__link">Pricing</a>
        <a href="https://www.google.com/" class="atmosphere-catering__link">Contact</a>
      </nav>
    </div>
</template>

<script setup lang="js">
import { ref } from 'vue'

const title = ref('Hello World')
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