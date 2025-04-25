<template>
  <div class="hero-banner"></div>
</template>

<script setup></script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;
.hero-banner {
  width: 100%;
  background-image:
    linear-gradient(to bottom, rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.85)),
    url("https://res.cloudinary.com/eddieebeling/image/upload/w_1920/v1744216764/catering_fqo33b.png");
  background-size: cover;
  background-position: bottom center;

  @media (max-width: $xs) {
    padding: 25% 0;
  }

  @media (min-width: $xs) and (max-width: $sm) {
    padding: 20% 0;
  }

  @media (min-width: $sm) and (max-width: $md) {
    padding: 20% 0;
  }

  @media (min-width: $md) and (max-width: $lg) {
    padding: 15% 0;
    background-attachment: fixed;
  }

  @media (min-width: $lg) {
    padding: 15% 0;
    background-attachment: fixed;
  }
}
</style>
