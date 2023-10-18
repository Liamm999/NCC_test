<template>
  <div class="navContainer">
    <div class="navContainer__nav" :class="{ flexDisplay: isOpen }">
      <span
        class="navContainer__nav__content"
        :class="{ textWhite: index === 0 }"
        v-for="(nav, index) in navContents"
        :key="index"
      >
        {{ nav }}
      </span>
      <span
        class="navContainer__nav__content navContainer__nav__content--close"
        @click="setDisplay"
        >Close</span
      >
    </div>
    <div class="navContainer__nav--secondary" @click="setDisplay">
      <div class="slash"></div>
      <div class="slash"></div>
      <div class="slash"></div>
    </div>
    <div class="navContainer__content">
      <div class="navContainer__main">
        <slot></slot>
      </div>
      <LayoutFooter />
    </div>
  </div>
</template>

<script>
import LayoutFooter from "./LayoutFooter.vue";

export default {
  name: "LayoutNavBar",
  components: { LayoutFooter },

  data() {
    return {
      navContents: ["Home", "Services", "News", "Blog", "Contact"],
      isOpen: false,
    };
  },

  methods: {
    setDisplay() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style lang="scss" scoped>
.navContainer {
  display: flex;
  height: 100vh;
  flex-direction: row;

  @media (max-width: 640px) {
    flex-direction: column;
  }

  &__nav {
    display: flex;
    flex-direction: column;
    width: 8rem;
    height: 100%;
    background-color: #191718;
    overflow-x: hidden;
    position: fixed;
    z-index: 1;
    left: 0;

    &__content {
      color: #aaa;
      padding: 10px;
      border-bottom: 1px solid #aaa;
      &:hover {
        @extend .textWhite;
        background-color: #5c5c5c;
      }
      &--close {
        display: none;
        width: 8rem;
        position: absolute;
        bottom: 0;
        border-top: 1px solid #aaa;
        border-bottom: 0;

        @media (max-width: 640px) {
          display: block;
        }
      }
    }

    &--secondary {
      display: inline-block;
      cursor: pointer;
      width: fit-content;
      margin-top: 2rem;
      margin-left: 2rem;
    }

    @media (max-width: 640px) {
      display: none;
    }
  }

  &__main {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 20px;
    margin-left: 8rem;

    @media (max-width: 640px) {
      margin-left: 0;
    }
  }
}

.textWhite {
  color: white;
}

.flexDisplay {
  display: flex;
}

.slash {
  width: 35px;
  height: 5px;
  background-color: #333;
  margin: 6px 0;
}
</style>
