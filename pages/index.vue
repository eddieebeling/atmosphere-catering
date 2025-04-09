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
  <div id="menus" class="atmosphere-catering__menus">MENU CONTENT</div>
  <div id="pricing" class="atmosphere-catering__pricing">PRICING CONTENT</div>
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
  { text: "Menus", anchor: "menus" },
  { text: "Pricing", anchor: "pricing" },
  { text: "Contact", anchor: "contact" },
]);
</script>

<style lang="scss">
@mixin respond-to($breakpoint) {
  @if $breakpoint == small {
    @media (max-width: 600px) {
      & {
        @content;
      }
    }
  } @else if $breakpoint == medium {
    @media (min-width: 601px) and (max-width: 900px) {
      & {
        @content;
      }
    }
  } @else if $breakpoint == large {
    @media (min-width: 901px) and (max-width: 1240px) {
      & {
        @content;
      }
    }
  } @else if $breakpoint == xlarge {
    @media (min-width: 1241px) {
      & {
        @content;
      }
    }
  }
}

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

    @include respond-to(small) {
      display: none;
    }
    @include respond-to(medium) {
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
    width: 100vw;
    background:
      linear-gradient(to bottom, rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.85)),
      url("https://res.cloudinary.com/eddieebeling/image/upload/v1744216764/catering_fqo33b.png")
        no-repeat center center;
    background-size: cover;
    @include respond-to(small) {
      min-height: 300px;
    }
    @include respond-to(medium) {
      min-height: 360px;
    }
    @include respond-to(large) {
      min-height: 380px;
      background-attachment: fixed;
    }
    @include respond-to(xlarge) {
      min-height: 400px;
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

    @include respond-to(small) {
      font-size: 3rem;
      max-width: 80%;
    }
    @include respond-to(medium) {
      max-width: 85%;
      font-size: 3.75rem;
    }
    @include respond-to(large) {
      max-width: 65%;
      font-size: 4rem;
    }
    @include respond-to(xlarge) {
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

    @include respond-to(large) {
      grid-template-columns: 1fr 1fr;
      grid-gap: 4rem;
      &.image-right {
        direction: rtl;
      }
    }
    @include respond-to(xlarge) {
      grid-template-columns: 1fr 1fr;
      grid-gap: 6rem;
      &.image-right {
        direction: rtl;
      }
    }

    color: rgba(255, 255, 255, 0.85);
    font-size: 2rem;
    line-height: 1;
    font-family: "Libre Caslon Display", serif;
    font-weight: 400;
    text-align: center;
    max-width: 1240px;
    text-align: left;
    padding: 3rem;

    @include respond-to(xlarge) {
      padding: 3rem 0;
    }

    h2 {
      font-family: "Roboto", sans-serif;
      font-family: "Libre Caslon Display", serif;
      font-size: 3rem;
      font-weight: 300;
      margin: 1.5rem 0;
      padding: 0;
      @include respond-to(small) {
        font-size: 2.25rem;
      }
      @include respond-to(medium) {
        font-size: 2.5rem;
      }
    }
    p {
      font-family: "Roboto", sans-serif;
      font-size: 1.25rem;
      line-height: 1.4;
      font-weight: 300;
      margin: 0 0 1rem 0;
      @include respond-to(small) {
        font-size: 1.125rem;
      }
      @include respond-to(medium) {
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

      @include respond-to(medium) {
        min-height: 420px;
      }
      @include respond-to(large) {
        min-height: 480px;
      }
      @include respond-to(xlarge) {
        min-height: 520px;
      }
    }
  }
  &__menus {
    display: flex;
    justify-content: center;
    align-items: center;
    color: rgba(255, 255, 255, 0.85);
    min-height: 300px;
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
    max-width: 1240px;
  }
}
</style>
