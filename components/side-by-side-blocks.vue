<template>
<side-by-side
    v-for="(item, index) in sideBySideContent"
    :id="item.id"
    :key="index"
    :block="item"
  ></side-by-side>
</template>

<script setup>
import { ref } from "vue";

const sideBySideContent = ref([
  {
    id: "catering",
    image:
      "https://res.cloudinary.com/eddieebeling/image/upload/w_1000/v1745322751/CORP_CATERING_Opt1Wok_wdidwj.jpg",
    alt: "Coporate Catering and Luncheons",
    heading: "Corporate Catering",
    content: `<p>We are Atmosphere Catering & Events — Arizona's premier, chef-driven, delivered catering provider. Serving all of Metro Phoenix and East Valley, we specialize in serving elevated lunches to medical & biotech offices, financial firms, tech, or virtually any place of business you may have.</p>
              <p>We pride ourselves on crafting thoughtfully curated menus, and preparing delicious, healthy meals, using the freshest quality ingredients around.</p>
              <p>Offering a host of inspired menu options, from Zesty Mediterranean and Vibrant Southwest to Island-style Hawaiian BBQ and Delectable Hand-Crafted Sandwiches — we're sure to amuse your senses.</p>`,
  },
  {
    id: "parties",
    image:
      "https://res.cloudinary.com/eddieebeling/image/upload/w_1000/v1745322751/PRIVATE-DINING_opt1_oga5mc.jpg",
    alt: "Private Dining and Intimate Parties",
    heading: "Private Dining & Intimate Parties",
    content: `<p>Hosting a brunch, lunch, dinner or private party soon? We do that too. At Atmosphere, we're in our element serving 5-20 person interactive private parties, featuring spirited menus and signature cocktails. We love to mix it up with you and your guests.</p>
              <p>Our focus ranges from tasty, elevated comfort food with bold flavors, to elegant lighter fare with subtle nuances, creating the perfect meal to suit your party. Chef Justin has traveled all over the globe picking up tidbits and recipes along the way. So, whether it's a family-style tomahawk ribeye & lobster, a cozy Bolognese, scrumptious shared small plates — or even New Orleans Creole, he can develop a menu with you that will blow your guests away.</p>
              <p>Call for pricing, and let's get creative together on a customized menu from your inspiration.</p>`,
  },
  {
    id: "events",
    image:
      "https://res.cloudinary.com/eddieebeling/image/upload/w_1000/v1745322743/EVENTS_CELEBRATION_BrunchParty1_othyfq.jpg",
    alt: "Events and Celebrations",
    heading: "Events & Celebrations",
    content: `<p>From Bar Mitzvahs to Fantasy Draft Day, and every milestone in between, if you have an event to celebrate, let Atmosphere take care of feeding your guests with style and grace.</p>
              <p>Atmosphere offers flexibility and creativity when it comes to preparing world class meals for you and your guests. Food is our passion, so together, we can come up with a menu to bring your vision to reality.</p>`,
  },
]);
</script>

<style lang="sass">
</style>