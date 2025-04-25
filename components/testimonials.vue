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
            <strong>{{ item.name }}</strong> &bull;
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
    text: "Atmosphere Catering is the best! The food was delicious and the service was impeccable.",
    name: "John Doe",
    position: "CEO",
    company: "Company Name",
    image:
      "https://res.cloudinary.com/eddieebeling/image/upload/w_300/v1745430144/16124205_1840922989518177_2606415304602943488_a_pdlovt.jpg",
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
    testimonialIndex.value =
      (testimonialIndex.value + 1) % testimonials.value.length;
  }, 7500);
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
