<template>
  <div class="testimonials">
    <div class="testimonials__content">
      <template v-for="(item, index) in testimonials" :key="index">
        <blockquote
          v-show="index === testimonialIndex"
          class="animate__animated animate__fadeIn"
        >
          <div class="testimonials__quote">"{{ item.text }}"</div>
          <div class="testimonials__five-stars">
            <star></star>
            <star></star>
            <star></star>
            <star></star>
            <star></star>
          </div>
          <div class="testimonials__attribution">
            <strong>{{ item.name }}</strong> &mdash;
            <span>{{ item.position }} at {{ item.company }}</span>
          </div>
        </blockquote>
      </template>
    </div>
  </div>
</template>

<script setup>
const testimonials = ref([
  {
    text: "In my experience, catering is almost always setting the floor for the Minimal Viable Product; yes it’s food, but it’s a chore to eat. Justin’s food is a whole other sport. It’s like having your favorite treat restaurant come to you. It’s incredibly good, and I can’t believe how much bad food I’ve eaten when this could have been an option.",
    name: "Luke K",
    position: "Founder & Producer",
    company: "Borah Media"
  },
  {
    text: "We are always blown away by Justin’s consistency serving delicious, flavorful and appetizing food. He delivers attention to every detail which makes an impeccable presentation. His ability to bring the best locally sourced ingredients and incredible flavors to every dish, makes for an exciting dining experience every time! We would trust him to cater any event because his passion and confidence for culinary arts go hand and hand.",
    name: "Sarah F",
    position: "Owner",
    company: "PürElement Hair Studio"
  },
  {
    text: "Atmosphere Catering provided an exceptional experience! The food was not only delicious but also presented with such elegance and care. Justin and his team went above and beyond to ensure everything was perfect. My offices love it!",
    name: "Candi E",
    position: "Uro-Oncology Account Manager",
    company: "Sumitomo Pharma America"
  },
]);
const testimonialIndex = ref(0);
const cycleTestimonials = () => {
  setInterval(() => {
    testimonialIndex.value =
      (testimonialIndex.value + 1) % testimonials.value.length;
  }, 20000);
};

onMounted(() => {
  cycleTestimonials();
});
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;

.testimonials {
  color: rgba(255, 255, 255, 0.85);
  padding: 8% 6%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;

  &__content {
  }

  &__quote {
    @include font-serif;
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

  &__five-stars {
    padding: 1rem 0;

    svg {
      height: 20px;
      width: 20px;
      margin: 0 0.5rem;
      fill: rgba(177, 116, 63, 0.8);
    }
  }

  &__attribution {
    padding: 1rem 0;
    font-size: 1.25rem;

    strong {
      font-weight: 600;
    }

    span {
      font-style: italic;
    }
  }
}
</style>
