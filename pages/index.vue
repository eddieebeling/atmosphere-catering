<template>
  <div class="atmosphere-catering__header">
    <nav class="atmosphere-catering__nav">
      <a
        v-for="(item, index) in leftNavLinks"
        :key="index"
        @click="scrollTo(item.anchor)"
        class="atmosphere-catering__link"
        >{{ item.text }}</a
      >
    </nav>
    <img
      :src="logoUrl"
      :alt="title"
      @click="scrollToTop"
      class="atmosphere-catering__logo"
    />
    <nav class="atmosphere-catering__nav">
      <a
        v-for="(item, index) in rightNavLinks"
        :href="item.url"
        :key="index"
        @click="scrollTo(item.anchor)"
        class="atmosphere-catering__link"
        >{{ item.text }}</a
      >
    </nav>
  </div>
  <div class="atmosphere-catering__hero"></div>
  <h1 class="atmosphere-catering__intro" v-html="intro"></h1>
  <div id="catering" class="atmosphere-catering__side-by-side image-right">
    <div class="atmosphere-catering__side-by-side--image"></div>
    <div class="atmosphere-catering__side-by-side--content">
      <h2>Professional Catering</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. In tristique
        dui non maximus ultrices. Cras euismod interdum justo, et porttitor
        lacus volutpat in. Phasellus varius consectetur elit, et luctus urna
        mattis id.
      </p>
      <p>
        Morbi quis quam sollicitudin, dictum dolor in, feugiat ex. Praesent
        efficitur odio quis tristique maximus. Sed convallis nec arcu et congue.
        Sed interdum velit in nunc ullamcorper, sit amet varius mi rhoncus.
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      </p>
    </div>
  </div>
  <div id="events" class="atmosphere-catering__side-by-side image-left">
    <div class="atmosphere-catering__side-by-side--image"></div>
    <div class="atmosphere-catering__side-by-side--content">
      <h2>Corporate & Private Events</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. In tristique
        dui non maximus ultrices. Cras euismod interdum justo, et porttitor
        lacus volutpat in. Phasellus varius consectetur elit, et luctus urna
        mattis id.
      </p>
      <p>
        Morbi quis quam sollicitudin, dictum dolor in, feugiat ex. Praesent
        efficitur odio quis tristique maximus. Sed convallis nec arcu et congue.
        Sed interdum velit in nunc ullamcorper, sit amet varius mi rhoncus.
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      </p>
    </div>
  </div>
  <div id="parties" class="atmosphere-catering__side-by-side image-right">
    <div class="atmosphere-catering__side-by-side--image"></div>
    <div class="atmosphere-catering__side-by-side--content">
      <h2>Parties &amp; Celebrations</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. In tristique
        dui non maximus ultrices. Cras euismod interdum justo, et porttitor
        lacus volutpat in. Phasellus varius consectetur elit, et luctus urna
        mattis id.
      </p>
      <p>
        Morbi quis quam sollicitudin, dictum dolor in, feugiat ex. Praesent
        efficitur odio quis tristique maximus. Sed convallis nec arcu et congue.
        Sed interdum velit in nunc ullamcorper, sit amet varius mi rhoncus.
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      </p>
    </div>
  </div>
  <div id="pricing" class="atmosphere-catering__menus">
    <h2>Catering &amp; Private Dining Pricing</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. In tristique dui
      non maximus ultrices. Cras euismod interdum justo, et porttitor lacus
      volutpat in. Phasellus varius consectetur elit, et luctus urna mattis id.
    </p>
    <div class="atmosphere-catering__menu-card-wrapper">
      <div class="atmosphere-catering__menu-card">
        <label>Catering for 5-20 People</label>
        <strong>$27.99 <sup>per person</sup></strong>
        <p>Morbi quis quam sollicitudin, dictum dolor in.</p>
        <ul>
          <li>Lorem ipsum, dolor sit amet consectetur</li>
          <li>Adipiscing elit. Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
        </ul>
      </div>
      <div class="atmosphere-catering__menu-card">
        <label>Catering for 20-50 People</label>
        <strong>$24.99 <sup>per person</sup></strong>
        <p>Morbi quis quam sollicitudin, dictum dolor in.</p>
        <ul>
          <li>Lorem ipsum, dolor sit amet consectetur</li>
          <li>Adipiscing elit. Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
        </ul>
      </div>
      <div class="atmosphere-catering__menu-card">
        <label>Private Dining Service</label>
        <strong>$34.99 <sup>per person</sup></strong>
        <p>Morbi quis quam sollicitudin, dictum dolor in.</p>
        <ul>
          <li>Lorem ipsum, dolor sit amet consectetur</li>
          <li>Adipiscing elit. Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
          <li>Quisquam, voluptatum</li>
        </ul>
      </div>
    </div>
  </div>
  <div id="menus" class="atmosphere-catering__pricing">MENU CONTENT</div>
  <div id="contact" class="atmosphere-catering__contact">CONTACT CONTENT</div>
  <div id="footer" class="atmosphere-catering__footer">
    <span
      >Copyright &copy; {{ currentYear }} Atmosphere Catering - All Rights
      Reserved.</span
    >
  </div>
</template>

<script setup lang="js">
import { ref } from "vue";

const title = ref("Atmosphere Catering");
const intro = ref(
  "CHEF QUALITY CATERING <span>for</span> EVENTS <span>of all sizes</span>",
);
const logoUrl = ref(
  "https://res.cloudinary.com/eddieebeling/image/upload/v1744216763/481854231_1419578952337847_6277475041924269601_n_putmyv.jpg",
);
const currentYear = ref(new Date().getFullYear());

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
  { text: "Events", anchor: "events" },
  { text: "Parties", anchor: "parties" },
]);
const rightNavLinks = ref([
  { text: "Pricing", anchor: "pricing" },
  { text: "Menus", anchor: "menus" },
  { text: "Contact", anchor: "contact" },
]);
</script>

<style lang="scss">
$xs: 600px;
$sm: 900px;
$md: 1240px;
$lg: 1440px;
$xl: 1920px;
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
    cursor: pointer;
  }
  &__title {
    font-size: 2rem;
    text-align: center;
  }
  &__nav {
    display: flex;
    justify-content: center;
    align-items: center;

    @media (max-width: $xs) {
      display: none;
    }
    @media (min-width: $xs) and (max-width: $sm) {
      display: none;
    }
  }
  &__link {
    color: rgba(255, 255, 255, 0.65);
    text-decoration: none;
    font-size: 0.9375rem;
    margin: 0 1.5rem;
    transition: color 0.3s ease;
    text-transform: uppercase;
    cursor: pointer;

    &:hover {
      color: rgba(255, 255, 255, 1);
    }
  }
  &__hero {
    width: 100%;
    background-image:
      linear-gradient(to bottom, rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.85)),
      url("https://res.cloudinary.com/eddieebeling/image/upload/v1744216764/catering_fqo33b.png");
    background-size: cover;
    background-position: center center;
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
  &__intro {
    padding: 8% 4% 6% 4%;
    color: rgba(255, 255, 255, 0.85);
    font-size: 4.5rem;
    width: 100vw;
    line-height: 1;
    font-family: "Libre Caslon Display", serif;
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
      font-size: 4rem;
    }
    @media (min-width: $md) {
      max-width: 45%;
      font-size: 5rem;
    }

    span {
      font-style: italic;
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
  &__side-by-side {
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 0;
    color: rgba(255, 255, 255, 0.85);
    font-size: 2rem;
    line-height: 1;
    font-family: "Libre Caslon Display", serif;
    font-weight: 400;
    text-align: center;
    max-width: $md;
    text-align: left;
    padding: 3rem;

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
      font-family: "Libre Caslon Display", serif;
      font-size: 3rem;
      font-weight: 300;
      margin: 1.5rem 0;
      padding: 0;
      @media (max-width: $xs) {
        font-size: 2.25rem;
      }
      @media (min-width: $xs) and (max-width: $sm) {
        font-size: 2.5rem;
      }
    }
    p {
      font-family: "Roboto", sans-serif;
      font-size: 1.25rem;
      line-height: 1.4;
      font-weight: 300;
      margin: 0 0 1rem 0;
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
      background: #2a2a2a;
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
  &__menus {
    display: flex;
    flex-direction: column;
    color: rgba(255, 255, 255, 0.85);
    min-height: 300px;
    padding: 3rem;
    margin-top: 3rem;
    border-top: solid 1px rgba(177, 116, 63, 0.5);
    border-bottom: solid 1px rgba(177, 116, 63, 0.5);

    > h2 {
      font-family: "Libre Caslon Display", serif;
      font-size: 3rem;
      font-weight: 300;
      margin: 1.5rem 0;
      padding: 0;
      text-align: center;
      @media (max-width: $xs) {
        font-size: 2.25rem;
      }
      @media (min-width: $xs) and (max-width: $sm) {
        font-size: 2.5rem;
      }
    }
    > p {
      font-family: "Roboto", sans-serif;
      font-size: 1.5rem;
      line-height: 1.5;
      font-weight: 300;
      margin: 0 0 1rem 0;
      text-align: center;
      max-width: 1100px;
      @media (max-width: $xs) {
        font-size: 1.125rem;
      }
      @media (min-width: $xs) and (max-width: $sm) {
        font-size: 1.25rem;
      }
    }
    button {
      font-family: "Roboto", sans-serif;
      font-weight: 700;
      cursor: pointer;
      border: solid 2px rgba(177, 116, 63, 1);
      background: transparent;
      color: rgba(177, 116, 63, 1);
      font-size: 0.9375rem;
      border-radius: 0.425rem;
      padding: 0.8125rem 1rem;
      text-transform: uppercase;
      width: 100%;
      max-width: 200px;
      margin: 2rem auto;
    }
  }
  &__menu-card-wrapper {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    max-width: $md;
    margin: 0 auto;
    padding: 4rem 2rem;

    @media (max-width: $xs) {
      flex-direction: column;
      align-items: center;
      padding: 1rem;
    }
  }
  &__menu-card {
    display: flex;
    flex-direction: column;
    border-radius: 0.8125rem;
    padding: 2rem 2.5rem;
    width: 100%;
    max-width: 280px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
    background: linear-gradient(135deg, #2a2a2a, #1f1f1f);

    &:nth-child(2n) {
      transform: scale(1.1);
      max-width: 260px;
    }

    label {
      font-family: "Roboto", sans-serif;
      color: rgba(177, 116, 63, 1);
      font-size: 1rem;
      font-weight: 700;
      padding: 0;
      text-transform: uppercase;
      text-align: left;
      margin-bottom: 0.5rem;
      @media (max-width: $xs) {
        font-size: 1.5rem;
      }
      @media (min-width: $xs) and (max-width: $sm) {
        font-size: 1.75rem;
      }
    }
    strong {
      font-family: "Libre Caslon Display", serif;
      font-size: 2.75rem;
      font-weight: 300;
      margin: 0.5rem 0;
      line-height: 1;
    }
    sup {
      font-size: 1.75rem;
      vertical-align: super;
    }
    span {
      font-size: 1.5rem;
    }
    p {
      font-family: "Roboto", sans-serif;
      line-height: 1.4;
      font-weight: 300;
      margin: 0 0 0.5rem 0;
      @media (max-width: $xs) {
        font-size: 1.125rem;
      }
      @media (min-width: $xs) and (max-width: $sm) {
        font-size: 1.125rem;
      }
    }
    ul {
      font-family: "Roboto", sans-serif;
      font-size: 0.9375rem;
      list-style-type: disc;
      margin: 0;
      padding: 0 0 0 1rem;

      li {
        text-align: left;
        padding: 0.25rem 0;
      }
    }
  }
  &__pricing {
    display: flex;
    justify-content: center;
    align-items: center;
    color: rgba(255, 255, 255, 0.85);
    min-height: 300px;
  }
  &__contact {
    display: flex;
    justify-content: center;
    align-items: center;
    color: rgba(255, 255, 255, 0.85);
    min-height: 300px;
  }
  &__footer {
    font-size: 0.8125rem;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    color: rgba(255, 255, 255, 0.5);
    border-top: solid 1px rgba(177, 116, 63, 0.5);
    padding: 1rem 0 3rem;
    width: 100%;
    max-width: $md;
  }
}
</style>
