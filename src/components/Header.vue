<template>
  <header class="header">
    <g-link
      to="/"
      tag="h1"
      class="name"
      :class="{ first: data.first_letter_only }"
    >
      <span
        class="word"
        :class="{ 'first-line': index === 0 && multiLine }"
        v-for="(word, index) in siteName"
        :key="index"
      >
        <span class="first-letter" v-if="data.first_letter_only && word[0]">{{
          word[0]
        }}</span>
        <span class="letter" v-if="data.first_letter_only">{{
          word.slice(1)
        }}</span>
        <span v-if="!data.first_letter_only">{{ word }}</span>
      </span>
    </g-link>

  </header>
</template>

<script>
import data from "@/data/theme.json";

export default {
  name: "Header",
  data() {
    return {
      data
    };
  },
  computed: {
    siteName() {
      return data.header_title.split(" ");
    },
    multiLine() {
      return this.siteName.length >= 1;
    }
  }
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  padding: 4rem 2rem 5rem 2rem;
  text-transform: none;
  letter-spacing: 0.1em;
  z-index: 100;
  opacity: 1;
  mix-blend-mode: difference;
  transition: opacity 0.5s ease;
  &.hidden {
    opacity: 0;
  }
}
.name {
  font-family: "Josefin Sans", sans-serif;
  text-transform: uppercase;
  color: lightcoral;
  font-size: 1.9rem;
  font-weight: 300;
  user-select: none;
  margin: 0;
  cursor: pointer;
  .word {
    margin-right: 0.5rem;
    &.first-line {
      display: block;
      margin-bottom: 0.5rem;
    }
    &:last-of-type {
      margin: 0;
    }
  }
  &.first {
    .letter {
      transition: opacity 0.15s ease;
      opacity: 0;
    }
    .first-letter {
      opacity: 1;
      font-family: 'UnifrakturMaguntia', serif;
      font-size: 3.5rem;
    }
    &:hover {
      .letter {
        opacity: 1;
      }
    }
  }
}
</style>
