<template>
  <div class="atmosphere-catering__header">
    <nav class="atmosphere-catering__nav">
      <a v-for="(item, index) in leftNavLinks" :key="index" @click="scrollTo(item.anchor)"
        class="atmosphere-catering__link">{{ item.text }}</a>
    </nav>
    <img :src="logoUrl" :alt="title" @click="scrollToTop" class="atmosphere-catering__logo" />
    <nav class="atmosphere-catering__nav">
      <a v-for="(item, index) in rightNavLinks" :href="item.url" :key="index" @click="scrollTo(item.anchor)"
        class="atmosphere-catering__link">{{ item.text }}</a>
    </nav>
  </div>
  <div class="atmosphere-catering__hero"></div>
  <h1 class="atmosphere-catering__intro" v-html="intro"></h1>
  <div id="catering" class="atmosphere-catering__side-by-side image-right">
    <div class="atmosphere-catering__side-by-side--image">
      <img src="https://res.cloudinary.com/eddieebeling/image/upload/w_1000/v1744225093/greek2_fkmxti.jpg"
        alt="Coporate Catering and Luncheons" />
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
      <img src="https://res.cloudinary.com/eddieebeling/image/upload/w_1000/v1745322751/PRIVATE-DINING_opt1_oga5mc.jpg"
        alt="Private Dining and Intimate Parties" />
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
        src="https://res.cloudinary.com/eddieebeling/image/upload/w_1000/v1745322743/EVENTS_CELEBRATION_BrunchParty1_othyfq.jpg"
        alt="Events and Celebrations" />
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
  <div id="testimonials" class="atmosphere-catering__testimonials">
    <!-- <h2>Don’t take our word for it, check out what our happy customers have to say!</h2> -->
    <div class="atmosphere-catering__testimonial-content">
      <template v-for="(item, index) in testimonials" :key="index">
        <blockquote v-show="index === testimonialIndex" class="animate__animated animate__fadeIn">
          <div class="atmosphere-catering__testimonial-quote">"{{ item.text }}"</div>
          <div class="atmosphere-catering__testimonial-five-stars">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
              <path
                d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z" />
            </svg>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
              <path
                d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z" />
            </svg>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
              <path
                d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z" />
            </svg>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
              <path
                d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z" />
            </svg>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
              <path
                d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z" />
            </svg>
          </div>
          <div class="atmosphere-catering__testimonial-attribution">
            <strong>{{ item.name }}</strong> &bull; <span>{{ item.position }} at {{ item.company }}</span>
          </div>
        </blockquote>
      </template>
    </div>
  </div>
  <div id="menus" class="atmosphere-catering__menus">
    <div class="atmosphere-catering__menu-card">
      <h2>Corporate Catering Menus</h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. </p>
    </div>
    <div class="atmosphere-catering__menu-card">
      <h3>Mediterranean</h3>
      <ul>
        <li>Grilled Lemon Vin Chicken Breast</li>
        <li>Fire Roasted Vegetables</li>
        <li>Greek Salad with Feta</li>
        <li>Organic Hummus & Pita</li>
        <li>Meraki Fruit Plate</li>
        <li>Pickled Red Onion & Tzatziki</li>
      </ul>
    </div>
    <div class="atmosphere-catering__menu-card">
      <h3>Hawaiian BBQ</h3>
      <ul>
        <li>Huli Huli Chicken</li>
        <li>Grilled Pineapple</li>
        <li>Coconut Jasmine Rice</li>
        <li>Chef J's Famous Island Mac Salad</li>
        <li>Ohana Green Salad</li>
        <li>Asian Sesame Ginger Dressing</li>
        <li>Aloha Fruit Plate</li>
        <li>Decadent Malasadas (Upon request)</li>
      </ul>
    </div>
    <div class="atmosphere-catering__menu-card">
      <h3>Southwestern</h3>
      <ul>
        <li>Sazón/Citrus Grilled Chicken</li>
        <li>Sautéed Fajita Vegetables</li>
        <li>Charred Corn Salad</li>
        <li>Cilantro Lime Dressing</li>
        <li>Spanish Rice</li>
        <li>Yucatán Black Beans</li>
        <li>Salsa/Sour Cream/Griddled Tortillas</li>
      </ul>
    </div>
    <div class="atmosphere-catering__menu-card">
      <h3>Hand-Crafted Sandwiches + Salad</h3>
      <ul>
        <li>Locally Sourced Breads &amp; Rolls</li>
        <li>Choice of:
          <ul>
            <li>Succulent Turkey Breast</li>
            <li>House Carved Roast Beef</li>
            <li>Italian Cured Meats</li>
          </ul>
        </li>
        <li>Various Cheeses</li>
        <li>Lettuce/Tomato/Pickled Red Onions</li>
        <li>Gourmet Condiments</li>
        <li>Fresh Fruit</li>
        <li>Spinach Strawberry Goat Cheese Salad</li>
      </ul>
    </div>
    <div class="atmosphere-catering__menu-card">
      <h3>Elegant Charcuterie</h3>
      <ul>
        <li>Assorted Meats</li>
        <li>Artisan Cheeses</li>
        <li>Seasonal Fruits &amp; Pickled Veg</li>
        <li>Dipping Breads + Crackers</li>
        <li>Sweet & Savory Spreads</li>
        <li>Fresh Green Salad</li>
      </ul>
    </div>
  </div>
  <div id="contact" class="atmosphere-catering__contact">
    <div class="atmosphere-catering__contact-content">
      <h2>Let's chat...</h2>
      <p>
        Call or email today for more information and to schedule your event, and
        let's get creative together!
      </p>
      <p>
        Email: <a href="mailto:chef@atmocatering.com">chef@atmocatering.com</a><br />
        Phone: <a href="tel:619-757-0480">619.757.0480</a>
      </p>
    </div>

    <form name="lead" action="/thank-you" class="atmosphere-catering__form" netlify>
      <label for="name" class="atmosphere-catering__form--label">
        <span>Name</span>
        <input type="text" id="name" name="name" autocomplete="name" required />
      </label>
      <label for="phone" class="atmosphere-catering__form--label">
        <span>Phone</span>
        <input type="phone" id="phone" name="phone" autocomplete="phone" required />
      </label>
      <label for="email" class="atmosphere-catering__form--label">
        <span>Email</span>
        <input type="email" id="email" name="email" autocomplete="email" required />
      </label>
      <label for="message" class="atmosphere-catering__form--label">
        <span>Event Details</span>
        <textarea id="message" name="message" required></textarea>
      </label>
      <div>
        <button type="submit">Send Message</button>
      </div>
    </form>
  </div>
  <div id="footer" class="atmosphere-catering__footer">
    <span>Copyright &copy; {{ currentYear }} Atmosphere Catering - All Rights
      Reserved.</span>
    <ul id="social" class="atmosphere-catering__social">
      <li class="atmosphere-catering__social--item">
        <a href="https://www.instagram.com/atmospherecatering/" target="_blank" rel="noopener noreferrer"
          class="atmosphere-catering__social--link"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
            <path
              d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
              fill="currentColor" />
          </svg></a>
      </li>
      <li class="atmosphere-catering__social--item">
        <a href="https://www.facebook.com/atmocatering/" target="_blank" rel="noopener noreferrer"
          class="atmosphere-catering__social--link"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
            <path
              d="M80 299.3V512H196V299.3h86.5l18-97.8H196V166.9c0-51.7 20.3-71.5 72.7-71.5c16.3 0 29.4 .4 37 1.2V7.9C291.4 4 256.4 0 236.2 0C129.3 0 80 50.5 80 159.4v42.1H14v97.8H80z"
              fill="currentColor" />
          </svg></a>
      </li>
      <li class="atmosphere-catering__social--item">
        <a href="https://www.linkedin.com/in/justinpalicki/" target="_blank" rel="noopener noreferrer"
          class="atmosphere-catering__social--link"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
            <path
              d="M100.3 448H7.4V148.9h92.9zM53.8 108.1C24.1 108.1 0 83.5 0 53.8a53.8 53.8 0 0 1 107.6 0c0 29.7-24.1 54.3-53.8 54.3zM447.9 448h-92.7V302.4c0-34.7-.7-79.2-48.3-79.2-48.3 0-55.7 37.7-55.7 76.7V448h-92.8V148.9h89.1v40.8h1.3c12.4-23.5 42.7-48.3 87.9-48.3 94 0 111.3 61.9 111.3 142.3V448z"
              fill="currentColor" />
          </svg></a>
      </li>
    </ul>
  </div>
</template>

<script setup lang="js">
import { ref, onMounted, computed } from "vue";

const title = ref("Atmosphere Catering");
const intro = ref(
  "ELEVATE YOUR ATMOSPHERE <span>Chef-driven catering for the tastefully refined</span>",
);
const logoUrl = ref(
  "https://res.cloudinary.com/eddieebeling/image/upload/v1745462447/atmo-logo_gtp2tr.jpg",
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

const testimonials = ref([
  {
    text: "Atmosphere Catering is the best! The food was delicious and the service was impeccable.",
    name: "John Doe",
    position: "CEO",
    company: "Company Name",
    image: "https://res.cloudinary.com/eddieebeling/image/upload/w_300/v1745430144/16124205_1840922989518177_2606415304602943488_a_pdlovt.jpg",
  },
  {
    text: "I can't recommend Atmosphere Catering enough! They made our event unforgettable.",
    name: "Jane Smith",
    position: "Event Planner",
    company: "Event Company",
  },
  {
    text: "The food was amazing and the staff was so friendly. I will definitely use them again!",
    name: "Bob Johnson",
    position: "Marketing Director",
    company: "Marketing Company",
  },
  {
    text: "Atmosphere Catering exceeded my expectations! The food was delicious and beautifully presented. My offices love it!",
    name: "Candi Ebeling",
    position: "Uro-Oncology Account Manager",
    company: "Sumitomo Pharma America",
  },
]);
const testimonialIndex = ref(0);
const cycleTestimonials = () => {
  setInterval(() => {
    testimonialIndex.value = (testimonialIndex.value + 1) % testimonials.value.length;
  }, 7500);
};

onMounted(() => {
  cycleTestimonials();
});
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

  &__menus {
    width: 100%;
    display: grid;
    grid-gap: 0;
    color: rgba(255, 255, 255, 0.85);
    font-size: 2rem;
    line-height: 1;
    font-family: "Libre Caslon Display", serif;
    padding: 3rem;
    max-width: 1280px;

    @media (min-width: $sm) {
      grid-template-rows: repeat(3, 1fr);
      grid-template-columns: repeat(2, 1fr);
      grid-gap: 1rem;
    }

    @media (min-width: $lg) {
      grid-template-rows: repeat(2, 1fr);
      grid-template-columns: repeat(3, 1fr);
      grid-gap: 1rem;
      padding: 3rem 0 5rem;
    }
  }

  &__menu-card {
    font-family: "Roboto", sans-serif;
    color: rgba(255, 255, 255, 0.85);
    font-size: 1.25rem;
    line-height: 1.5;
    padding: 2.5rem 3rem;
    border: solid 1px rgba(177, 116, 63, 0.5);

    &:first-child {
      border: none;
      padding-left: 0;
    }

    h2 {
      font-family: "Libre Caslon Display", serif;
      font-size: 2.5rem;
      line-height: 1.1;
      margin: 0 0 1rem 0;
      color: #fff
    }

    h3 {
      font-family: "Libre Caslon Display", serif;
      font-size: 1.5rem;
      line-height: 1.1;
      text-transform: uppercase;
      margin: 0 0 1rem 0;
      color: rgba(177, 116, 63, 1);

    }

    ul {
      list-style: none;
      padding: 0;
      margin: 0;
      font-size: 1.125rem;

      li {
        padding: 0.25rem 0;
        position: relative;
      }

      ul li {
        padding: .0125rem 0;
        padding-left: .8125rem;
        font-size: 1rem;

        &::before {
          content: "•";
          padding-right: .8125rem;
        }
      }
    }
  }

  &__testimonials {
    color: rgba(255, 255, 255, 0.85);
    padding: 8% 6%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  &__testimonial-quote {
    font-family: "Libre Caslon Display", serif;
    font-size: 2rem;
    line-height: 1.1;
    padding: 1rem 0;
    margin: 0;

    @media (max-width: $xs) {
      font-size: 1.75rem;
    }

    @media (min-width: $xs) and (max-width: $sm) {
      font-size: 2rem;
    }
  }

  &__testimonial-five-stars {
    padding: 1rem 0;

    svg {
      height: 20px;
      width: 20px;
      margin: 0 0.5rem;
      fill: rgba(177, 116, 63, 0.8);
    }
  }

  &__testimonial-attribution {
    padding: 1rem 0;
    font-size: 1.25rem;

    strong {
      font-weight: 600;
    }

    span {
      font-style: italic;
    }
  }

  &__contact {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    color: rgba(255, 255, 255, 0.85);
    min-height: 300px;
    width: 100%;
    max-width: 1240px;
    padding: 3rem;

    @media (min-width: $sm) and (max-width: $md) {
      flex-direction: row;
      padding: 3rem 0 5rem;
    }

    @media (min-width: $md) {
      flex-direction: row;
      padding: 3rem 0 5rem;
    }

    @media (min-width: $lg) {
      flex-direction: row;
      padding: 3rem 0 5rem;
    }

    h2 {
      font-family: "Libre Caslon Display", serif;
      font-size: 2.75rem;
      font-weight: 300;
      margin: 2.5rem 0 1.5rem 0;
      padding: 0;
      direction: ltr;
      max-width: 70%;

      @media (max-width: $xs) {
        font-size: 2.25rem;
      }

      @media (min-width: $xs) and (max-width: $sm) {
        font-size: 2.5rem;
      }
    }

    p {
      font-size: 1.25rem;
      line-height: 1.5;
    }

    a {
      color: rgba(177, 116, 63, 0.8);
      text-decoration: none;
      font-size: 1.25rem;
      line-height: 1.5;
      transition: color 0.3s ease;

      &:hover {
        color: rgba(177, 116, 63, 0.9);
      }
    }
  }

  &__contact-content {
    width: 100%;
    padding-right: 6%;
  }

  &__form {
    display: flex;
    flex-direction: column;
    width: 100%;

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

  &__profile-pic {
    padding: 2rem 0;
    display: inline-block;

    img {
      width: 160px;
      border-radius: 100%;
      object-fit: cover;
      border: solid 6px transparent;
      outline: solid 3px rgb(225, 49, 124);
    }
  }
}
</style>
