<template>
  <div class="footerContainer"><p>Copyright © 2021</p></div>
</template>

<script>
export default {
  name: "LayoutFooter",
};
</script>

<style lang="scss" scoped>
.footerContainer {
  width: 100%;
  padding: 30px 0;
  color: #3e3e3e;
  border-top: 1px solid #aaa;

  @media (min-width: 1280px) {
    position: absolute;
    bottom: 0;
    left: 0;
  }
  
  & p {
    margin: 0 14.75rem;

    @media (max-width: 640px) {
      text-align: center;
      margin: 0;
    }
  }
}
</style>
