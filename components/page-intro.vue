<template>
  <h1 class="page-intro">
    {{ intro }}<span>{{ subIntro }}</span>
  </h1>
</template>

<script setup>
const intro = ref("ELEVATE YOUR ATMOSPHERE");
const subIntro = ref("Chef-driven catering for the tastefully refined");
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;
.page-intro {
  padding: 8% 4% 6% 4%;
  color: rgba(255, 255, 255, 0.85);
  font-size: 3.5rem;
  width: 100vw;
  line-height: 1.2;
  @include font-serif;
  font-weight: 400;
  text-align: center;
  margin: 0;

  @media (max-width: $xs) {
    font-size: 3rem;
    max-width: 80%;
  }

  @media (min-width: $xs) and (max-width: $sm) {
    max-width: 85%;
    font-size: 3.75rem;
  }

  @media (min-width: $sm) and (max-width: $md) {
    max-width: 65%;
    font-size: 3rem;
  }

  @media (min-width: $md) {
    max-width: 80%;
    font-size: 4.5rem;
  }

  span {
    display: block;
    font-style: italic;
    font-size: 3.25rem;
  }

  &::after {
    content: "";
    display: block;
    width: 160px;
    height: 3px;
    background: rgba(177, 116, 63, 1);
    margin: 2.5rem auto;
  }
}
</style>
