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
    <div class="atmosphere-catering__side-by-side--image">
      <img
        src="https://res.cloudinary.com/eddieebeling/image/upload/v1745322748/CORP_CATERING-Opt2_or_TESTIMONIALS_Dr_qapgtx.jpg"
        alt="Coporate Catering and Luncheons"
        style="
          width: 100%;
          height: 100%;
          object-fit: cover;
          object-position: center;
        "
      />
    </div>
    <div class="atmosphere-catering__side-by-side--content">
      <h2>Corporate Catering</h2>
      <p>
        We are Atmosphere Catering &amp; Events — Arizona's premier,
        chef-driven, delivered catering provider. Serving all of Metro Phoenix
        and East Valley, we specialize in serving elevated lunches to medical
        &amp; biotech offices, financial firms, tech, or virtually any place of
        business you may have.
      </p>
      <p>
        We pride ourselves on crafting thoughtfully curated menus, and preparing
        delicious, healthy meals, using the freshest quality ingredients around.
      </p>
      <p>
        Offering a host of inspired menu options, from Zesty Mediterranean and
        Vibrant Southwest to Island-style Hawaiian BBQ and Delectable
        Hand-Crafted Sandwiches — we're sure to amuse your senses.
      </p>
    </div>
  </div>
  <div id="parties" class="atmosphere-catering__side-by-side image-left">
    <div class="atmosphere-catering__side-by-side--image">
      <img
        src="https://res.cloudinary.com/eddieebeling/image/upload/v1745322759/Cheers_plcweb.jpg"
        alt="Private Dining and Intimate Parties"
        style="
          width: 100%;
          height: 100%;
          object-fit: cover;
          object-position: center;
        "
      />
    </div>
    <div class="atmosphere-catering__side-by-side--content">
      <h2>Private Dining &plus; Intimate Parties</h2>
      <p>
        Hosting a brunch, lunch, dinner or private party soon? We do that too.
        At Atmosphere, we're in our element serving 5-20 person interactive
        private parties, featuring spirited menus and signature cocktails. We
        love to mix it up with you and your guests.
      </p>
      <p>
        Our focus ranges from tasty, elevated comfort food with bold flavors, to
        elegant lighter fare with subtle nuances, creating the perfect meal to
        suit your party. Chef Justin has traveled all over the globe picking up
        tidbits and recipes along the way. So, whether it's a family-style
        tomahawk ribeye &amp; lobster, a cozy Bolognese, scrumptious shared
        small plates — or even New Orleans Creole, he can develop a menu with
        you that will blow your guests away.
      </p>
      <p>
        Call for pricing, and let's get creative together on a customized menu
        from your inspiration.
      </p>
    </div>
  </div>
  <div id="events" class="atmosphere-catering__side-by-side image-right">
    <div class="atmosphere-catering__side-by-side--image">
      <img
        src="https://res.cloudinary.com/eddieebeling/image/upload/v1745322743/EVENTS_CELEBRATION_BrunchParty1_othyfq.jpg"
        alt="Events and Celebrations"
        style="
          width: 100%;
          height: 100%;
          object-fit: cover;
          object-position: center;
        "
      />
    </div>
    <div class="atmosphere-catering__side-by-side--content">
      <h2>Events &plus; Celebrations</h2>
      <p>
        From Bar Mitzvahs to Fantasy Draft Day, and every milestone in between,
        if you have an event to celebrate, let Atmosphere take care of feeding
        your guests with style and grace.
      </p>
      <p>
        Atmosphere offers flexibility and creativity when it comes to preparing
        world class meals for you and your guests. Food is our passion, so
        together, we can come up with a menu to bring your vision to reality.
      </p>
    </div>
  </div>
  <div id="testimonials" class="atmosphere-catering__contact">
    TESTIMONIAL CONTENT
  </div>
  <div id="menus" class="atmosphere-catering__contact">MENU CONTENT</div>
  <div id="contact" class="atmosphere-catering__contact">
    <h2>Let's chat...</h2>
    <form
      name="contact"
      method="POST"
      data-netlify="true"
      class="atmosphere-catering__form"
    >
      <label for="name" class="atmosphere-catering__form--label">
        <span>Name</span>
        <input type="text" id="name" name="name" autocomplete="name" required />
      </label>
      <label for="email" class="atmosphere-catering__form--label">
        <span>Email</span>
        <input
          type="email"
          id="email"
          name="email"
          autocomplete="email"
          required
        />
      </label>
      <label for="phone" class="atmosphere-catering__form--label">
        <span>Phone</span>
        <input
          type="phone"
          id="phone"
          name="phone"
          autocomplete="phone"
          required
        />
      </label>
      <label for="message" class="atmosphere-catering__form--label">
        <span>Message</span>
        <textarea id="message" name="message" required></textarea>
      </label>
      <div>
        <button type="submit">Send Message</button>
      </div>
    </form>
  </div>
  <div id="footer" class="atmosphere-catering__footer">
    <span
      >Copyright &copy; {{ currentYear }} Atmosphere Catering - All Rights
      Reserved.</span
    >
    <ul id="social" class="atmosphere-catering__social">
      <li class="atmosphere-catering__social--item">
        <a
          href="https://www.instagram.com/atmospherecatering/"
          target="_blank"
          rel="noopener noreferrer"
          class="atmosphere-catering__social--link"
          ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
            <path
              d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
              fill="currentColor"
            /></svg
        ></a>
      </li>
      <li class="atmosphere-catering__social--item">
        <a
          href="https://www.facebook.com/atmocatering/"
          target="_blank"
          rel="noopener noreferrer"
          class="atmosphere-catering__social--link"
          ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
            <path
              d="M80 299.3V512H196V299.3h86.5l18-97.8H196V166.9c0-51.7 20.3-71.5 72.7-71.5c16.3 0 29.4 .4 37 1.2V7.9C291.4 4 256.4 0 236.2 0C129.3 0 80 50.5 80 159.4v42.1H14v97.8H80z"
              fill="currentColor"
            /></svg
        ></a>
      </li>
      <li class="atmosphere-catering__social--item">
        <a
          href="https://www.linkedin.com/company/atmosphere-catering/"
          target="_blank"
          rel="noopener noreferrer"
          class="atmosphere-catering__social--link"
          ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
            <path
              d="M100.3 448H7.4V148.9h92.9zM53.8 108.1C24.1 108.1 0 83.5 0 53.8a53.8 53.8 0 0 1 107.6 0c0 29.7-24.1 54.3-53.8 54.3zM447.9 448h-92.7V302.4c0-34.7-.7-79.2-48.3-79.2-48.3 0-55.7 37.7-55.7 76.7V448h-92.8V148.9h89.1v40.8h1.3c12.4-23.5 42.7-48.3 87.9-48.3 94 0 111.3 61.9 111.3 142.3V448z"
              fill="currentColor"
            /></svg
        ></a>
      </li>
    </ul>
  </div>
</template>

<script setup lang="js">
import { ref } from "vue";

const title = ref("Atmosphere Catering");
const intro = ref(
  "ELEVATE YOUR ATMOSPHERE <span>Chef-driven catering for the tastefully refined</span>",
);
const logoUrl = ref(
  "https://res.cloudinary.com/eddieebeling/image/upload/v1745371966/atmosphere-logo-final_wi3i9n.jpg",
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
      url("https://res.cloudinary.com/eddieebeling/image/upload/v1745322713/shutterstock_775458475_jmuuj2.jpg");
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
    font-size: 3.5rem;
    width: 100vw;
    line-height: 1.2;
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
      font-family: "Roboto", sans-serif;
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
  &__contact {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: rgba(255, 255, 255, 0.85);
    min-height: 300px;
    padding: 2% 4% 8% 4%;
    h2 {
      font-family: "Libre Caslon Display", serif;
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

    form {
      display: flex;
      flex-direction: column;
    }
  }
  &__form {
    display: flex;
    flex-direction: column;

    button[type="submit"] {
      font-family: "Roboto", sans-serif;
      background: rgba(177, 116, 63, 0.8);
      text-transform: uppercase;
      color: #fff;
      font-weight: 600;
      font-size: 0.9375rem;
      padding: 0.9375rem 1.5rem;
      border-radius: 0.25rem;
      border: none;
      cursor: pointer;
      margin-top: 1rem;
      transition: all 0.2s ease-in-out;

      &:hover {
        background: rgba(177, 116, 63, 0.9);
        transform: scale(1.05);
      }
    }
  }
  &__form--label {
    padding: 0.8125rem 0;
    font-size: 1.125rem;
    min-width: 400px;

    span {
      display: block;
      font-size: 0.9375rem;
      margin-bottom: 0.5rem;
      color: rgba(255, 255, 255, 0.85);
      text-transform: uppercase;
      font-weight: 600;
    }

    input,
    textarea {
      font-family:
        "SF Mono", "Monaco", "Inconsolata", "Fira Mono", "Droid Sans Mono",
        "Source Code Pro", monospace;
      background: #1a1a1a;
      border: solid 1px rgba(177, 116, 63, 0.5);
      border-radius: 0.25rem;
      padding: 1rem;
      width: 100%;
      color: #fff;

      &:focus {
        outline: none;
        border: solid 1px rgba(177, 116, 63, 1);
        box-shadow: 0 0 0 2px rgba(177, 116, 63, 0.5);
      }
    }
    textarea {
      height: 140px;
    }
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
  &__social {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    list-style: none;
    margin: 0;
    transition: all 0.2s ease-in-out;
    svg {
      height: 20px;
      width: 20px;
    }
  }
  &__social--item {
    margin: 0 0 0 1rem;
    padding: 0;
    cursor: pointer;
  }
  &__social--link {
    color: rgba(255, 255, 255, 0.5);
    font-size: 1.5rem;
    transition: color 0.3s ease;

    &:hover {
      color: rgba(255, 255, 255, 1);

      svg {
        transform: scale(1.1);
      }
    }
  }
}
</style>
