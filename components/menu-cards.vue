<template>
  <div class="menu-cards">
    <div class="menu-cards__card">
      <h2 class="menu-cards__heading">{{ heading }}</h2>
    </div>
    <div
      v-for="(menu, index) in menuData"
      :key="index"
      class="menu-cards__card"
    >
      <h3 class="menu-cards__title">{{ menu.title }}</h3>
      <ul class="menu-cards__list">
        <li
          v-for="(item, idx) in menu.items"
          :key="idx"
          class="menu-cards__list-item"
          v-html="item"
        ></li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const heading = ref("Event & Corporate Catering Menus");
const menuData = ref([
  {
    title: "Mediterranean",
    items: [
      "Grilled Lemon Vin Chicken Breast",
      "Fire Roasted Vegetables",
      "Greek Salad with Feta",
      "Organic Hummus & Pita",
      "Meraki Fruit Plate",
      "Pickled Red Onion & Tzatziki",
    ],
  },
  {
    title: "Hawaiian BBQ",
    items: [
      "Huli Huli Chicken",
      "Grilled Pineapple",
      "Coconut Jasmine Rice",
      "Chef J's Famous Island Mac Salad",
      "Ohana Green Salad",
      "Asian Sesame Ginger Dressing",
      "Aloha Fruit Plate",
      "Decadent Malasadas (Upon request)",
    ],
  },
  {
    title: "Southwestern",
    items: [
      "Sazón/Citrus Grilled Chicken",
      "Sautéed Fajita Vegetables",
      "Charred Corn Salad",
      "Cilantro Lime Dressing",
      "Spanish Rice",
      "Yucatán Black Beans",
      "Salsa/Sour Cream/Griddled Tortillas",
    ],
  },
  {
    title: "Hand-Crafted Sandwiches + Salad",
    items: [
      "Locally Sourced Breads & Rolls",
      `Choice of:
      <ul>
        <li>Succulent Turkey Breast</li>
        <li>House Carved Roast Beef</li>
        <li>Italian Cured Meats</li>
      </ul>`,
      "Various Cheeses",
      "Lettuce/Tomato/Pickled Red Onions",
      "Gourmet Condiments",
      "Fresh Fruit",
      "Spinach Strawberry Goat Cheese Salad",
    ],
  },
  {
    title: "Elegant Charcuterie",
    items: [
      "Assorted Meats",
      "Artisan Cheeses",
      "Seasonal Fruits & Pickled Veg",
      "Dipping Breads + Crackers",
      "Sweet & Savory Spreads",
      "Fresh Green Salad",
    ],
  },
]);
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;

.menu-cards {
  width: 100%;
  display: grid;
  grid-gap: 0;
  color: rgba(255, 255, 255, 0.85);
  font-size: 2rem;
  line-height: 1;
  padding: 2rem;
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

  &__heading {
    @include font-serif;
    font-size: 2.5rem;
    line-height: 1.1;
    margin: 0 0 1rem 0;
    color: #fff;
  }

  &__title {
    @include font-serif;
    font-size: 1.5rem;
    font-weight: 700;
    line-height: 1.1;
    text-transform: uppercase;
    margin: 0 0 1rem 0;
    color: rgba(177, 116, 63, 1);
  }

  &__card {
    @include font-sans-serif;
    color: rgba(255, 255, 255, 0.85);
    font-size: 1.25rem;
    line-height: 1.5;
    padding: 2.5rem 3rem;
    border: solid 1px rgba(177, 116, 63, 0.5);

    &:first-child {
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      border: none;
      background-image:
        linear-gradient(to bottom, rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.85)),
        url("https://res.cloudinary.com/eddieebeling/image/upload/h_800/v1745322730/Huli_k78sc4.jpg");
      background-size: cover;
    }
  }

  &__list {
    list-style: none;
    padding: 0;
    margin: 0;
    font-size: 1.125rem;
  }

  &__list-item {
    padding: 0.25rem 0;
    position: relative;

    ul {
      padding-left: 1.25rem;
    }

    li {
      padding: 0.0125rem 0;
      font-size: 1rem;
      list-style: disc;
    }
  }
}
</style>
