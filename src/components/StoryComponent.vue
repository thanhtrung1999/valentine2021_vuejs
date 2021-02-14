<template>
  <section class="main-story">
    <h2 class="main-story__heading" v-if="story.heading !== ''">{{ story.heading }}</h2>
    <div class="main-story__content" v-html="story.content"></div>
    <h3 class="main-story__footer" v-if="story.footer !== ''">{{ story.footer }}</h3>
  </section>
</template>

<script>
export default {
  name: "story-component",
  props: {
    story: Object,
  },
};
</script>

<style lang="scss" scoped>
.main-story {
  &__heading {
    font-family: 'Pacifico', cursive;
    font-size: 2.2rem;
  }
  &__content {
    font-family: 'Dancing Script', cursive;
    font-size: 1.4rem;
  }
  &__footer {
    font-family: 'Cormorant Upright', serif;
    font-size: 1.9rem;
    text-transform: uppercase;
    margin-top: 1.2rem;
  }
}
</style>