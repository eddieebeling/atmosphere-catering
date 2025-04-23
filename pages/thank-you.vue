<template>
  <div class="thank-you animate__animated animate__fadeIn">
    <h1>{{ heading }}</h1>
    <p>{{ message }}</p>
  </div>
</template>

<script setup lang="js">
const heading = ref("Thank You!");
const message = ref(
  "Your message has been received. We will contact you shortly.",
);

setTimeout(async () => {
  await navigateTo("/");
}, 5000);
</script>

<style lang="scss">
.thank-you {
  font-family: "Roboto", sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
  color: #fff;
  text-align: center;

  h1 {
    color: rgba(255, 255, 255, 0.85);
    font-size: 3.5rem;
    width: 100vw;
    line-height: 1.2;
    font-family: "Libre Caslon Display", serif;
    font-weight: 400;
    text-align: center;
    margin: 0;
  }
  p {
    font-family: "Roboto", sans-serif;
    font-size: 1.25rem;
    line-height: 1.5;
    font-weight: 300;
    margin: 0 0 1rem 0;
  }
}
</style>
