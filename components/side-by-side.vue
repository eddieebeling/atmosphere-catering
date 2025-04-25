<template>
  <div class="side-by-side" :class="imageClass">
    <div class="side-by-side--image">
      <img :src="block.image" :alt="block.alt" />
    </div>
    <div class="side-by-side--content">
      <h2>{{ block.heading }}</h2>
      <div v-html="block.content"></div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  block: Object,
});

const imageClass = computed(() => {
  return props.block.id === "parties" ? "image-left" : "image-right";
});
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;
.side-by-side {
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 0;
  color: rgba(255, 255, 255, 0.85);
  font-size: 2rem;
  line-height: 1;
  @include font-serif;
  font-weight: 400;
  text-align: center;
  max-width: $md;
  text-align: left;
  padding: 2rem;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
  }

  @media (min-width: $sm) and (max-width: $md) {
    grid-template-columns: 1fr 1fr;
    grid-gap: 4rem;

    &.image-right {
      direction: rtl;
    }
  }

  @media (min-width: $md) {
    padding: 3rem 0;
    grid-template-columns: 1fr 1fr;
    grid-gap: 6rem;

    &.image-right {
      direction: rtl;
    }
  }

  h2 {
    @include font-serif;
    font-size: 2.75rem;
    font-weight: 300;
    margin: 1.5rem 0;
    padding: 0;
    direction: ltr;

    @media (max-width: $xs) {
      font-size: 2.25rem;
    }

    @media (min-width: $xs) and (max-width: $sm) {
      font-size: 2.5rem;
    }
  }

  p {
    @include font-sans-serif;
    font-size: 1.25rem;
    line-height: 1.5;
    font-weight: 300;
    margin: 0 0 1rem 0;
    direction: ltr;

    @media (max-width: $xs) {
      font-size: 1.125rem;
    }

    @media (min-width: $xs) and (max-width: $sm) {
      font-size: 1.125rem;
    }
  }

  span {
    font-style: italic;
  }

  &--content {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  &--image {
    height: 100%;
    background: rgb(42, 42, 42);
    background-position: center center;
    background-size: cover;
    min-height: 300px;

    @media (min-width: $xs) and (max-width: $sm) {
      min-height: 420px;
    }

    @media (min-width: $sm) and (max-width: $md) {
      min-height: 480px;
    }

    @media (min-width: $md) {
      min-height: 520px;
    }
  }
}
</style>
