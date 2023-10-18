<template>
  <div class="navContainer">
    <div
      class="navContainer__nav"
      :class="{ flexDisplay: isOpen }"
      @focusout="setDisplay"
    >
      <span
        class="navContainer__nav__content"
        :class="{ textWhite: index === 0 }"
        v-for="(nav, index) in navContents"
        :key="index"
      >
        {{ nav }}
      </span>
    </div>
    <div class="navContainer__nav--secondary" @click="setDisplay">
      Click here to open side bar
    </div>
    <div class="navContainer__main">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "LayoutNavBar",

  data() {
    return {
      navContents: ["Home", "Services", "News", "Blog", "Contact"],
      isOpen: false,
    };
  },

  methods: {
    setDisplay() {
      this.isOpen = !this.isOpen;
      console.log(this.isOpen);
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
    }

    &--secondary {
      width: 6rem;
      margin-top: 2rem;
      margin-left: 2rem;
      font-size: 12px;
      color: blue;
      text-decoration: underline;
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
</style>
