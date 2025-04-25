<template>
  <div class="atomosphere-catering animate__animated animate__fadeIn">
    <NuxtPage />
  </div>
</template>

<script setup>
useHead({
  title:
    "Atmosphere Catering - Chef-driven catering for the tastefully refined",
  meta: [
    {
      name: "description",
      content:
        "Elevate your atmosphere. Chef-driven catering for the tastefully refined.",
    },
    {
      name: "keywords",
      content:
        "Professional Catering for Parties, Events, Celebrations, and Private Dining in Metro Phoenix, Mesa, Tempe, Chandler, Gilbert, and Scottsdale, Arizona.",
    },
  ],
  bodyAttrs: {
    class: "dark-theme",
  },
});
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;
@use "animate.css/animate" as *;
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Libre+Caslon+Display&display=swap");

html {
  box-sizing: border-box;
}
* {
  box-sizing: inherit;
}
body {
  margin: 0;
  padding: 0;
  @include font-sans-serif;
  background: rgb(0, 0, 0);
}

.atomosphere-catering {
  @include font-sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
