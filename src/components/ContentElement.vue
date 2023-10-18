<template>
  <ContentDescription />
  <div class="elementContainer">
    <div
      v-for="(element, index) in elements"
      :key="index"
      class="elementContainer__content"
    >
      <h2>Lorem ipsum dolor sit amet</h2>
      <img :src="element.imgSrc" class="elementContainer__content__img" />
      <p class="elementContainer__content__description">
        {{ element.description }}
      </p>
    </div>
  </div>
</template>

<script>
import ContentDescription from "./ContentDescription.vue";
export default {
  name: "ContentElement",
  components: {
    ContentDescription,
  },

  props: {
    elements: {
      type: Array,
      default: () => [
        {
          imgSrc: String,
          description: String,
        },
      ],
    },
  },
};
</script>

<style lang="scss" scoped>
img {
  margin-bottom: 0;
}
.elementContainer {
  display: flex;
  gap: 50px;
  margin: 0 110px;
  padding-bottom: 2.5rem;

  @media (max-width: 1024px) {
    flex-direction: column;
  }

  @media (max-width: 640px) {
    margin: 16px;
  }

  &__content {
    &__img {
      width: 128px;
      height: 128px;
      float: left;
      shape-outside: image();
      margin: 4px 16px;
    }
  }
}
</style>
