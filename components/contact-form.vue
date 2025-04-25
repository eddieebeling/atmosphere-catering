<template>
  <form name="lead" action="/thank-you" class="form" netlify>
    <label for="name" class="form__label">
      <span>Name</span>
      <input type="text" id="name" name="name" autocomplete="name" required />
    </label>
    <label for="phone" class="form__label">
      <span>Phone</span>
      <input
        type="phone"
        id="phone"
        name="phone"
        autocomplete="phone"
        required
      />
    </label>
    <label for="email" class="form__label">
      <span>Email</span>
      <input
        type="email"
        id="email"
        name="email"
        autocomplete="email"
        required
      />
    </label>
    <label for="message" class="form__label">
      <span>Event Details</span>
      <textarea id="message" name="message" required></textarea>
    </label>
    <div>
      <button type="submit">Send Message</button>
    </div>
  </form>
</template>

<script setup></script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;

.form {
  display: flex;
  flex-direction: column;
  width: 100%;

  button[type="submit"] {
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

  &__label {
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
}
</style>
