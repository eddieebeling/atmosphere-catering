<template>
    <div class="contact">
        <div class="contact__content">
            <h2>Let's chat...</h2>
            <p>
                Call or email today for more information and to schedule your event, and
                let's get creative together!
            </p>
            <p>
                Email: <a :href="`mailto:${email}`">{{ email }}</a><br />
                Phone: <a :href="`tel:${phone}`">{{ phone }}</a>
            </p>
        </div>
        <form name="lead" action="/thank-you" class="contact__form" netlify>
            <label for="name" class="contact__form-label">
                <span>Name</span>
                <input type="text" id="name" name="name" autocomplete="name" required />
            </label>
            <label for="phone" class="contact__form-label">
                <span>Phone</span>
                <input type="phone" id="phone" name="phone" autocomplete="phone" required />
            </label>
            <label for="email" class="contact__form-label">
                <span>Email</span>
                <input type="email" id="email" name="email" autocomplete="email" required />
            </label>
            <label for="message" class="contact__form-label">
                <span>Event Details</span>
                <textarea id="message" name="message" required></textarea>
            </label>
            <div class="contact__form-button">
                <!-- Form Button -->
                <button type="submit">Send Message</button>
                <!-- <input type="submit" value="Send Message" /> -->
            </div>
        </form>
    </div>
</template>

<script setup>
import { ref } from "vue";
const email = ref("chef@atmocatering.com");
const phone = ref("619-757-0480");
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;

.contact {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    color: rgba(255, 255, 255, 0.85);
    min-height: 300px;
    width: 100%;
    max-width: 1240px;
    padding: 2rem;

    @media (min-width: $sm) and (max-width: $md) {
        flex-direction: row;
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

    &__content {
        width: 100%;
        padding-right: 6%;
    }

    &__form {
        display: flex;
        flex-direction: column;
        width: 100%;
    }

    &__form-label {
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
            @include font-monospace;
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

    &__form-button {

        button[type="submit"],
        input[type="submit"] {
            @include font-sans-serif;
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
