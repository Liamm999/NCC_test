<template>
  <div class="descriptionContainer">
    <h3>Lorem ipsum dolor sit asmet?</h3>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed tristique
      consequat placerat. Vestibulum auctor pellentesque sem, eu posuere erat
      hendrerit quis. Maecenas vel consequat turpis. Nam facilisis, ligula in
      mattis sodales, augue justo tristique nulla, sed lacinia ante eros ut mi.
      Morbi vitae diam augue. Aliquam vel mauris a nibh auctor commodo. Praesent
      et nisi eu justo eleifend convallis. Quisque suscipit maximus vestibulum.
      Phasellus congue mollis orci, sit amet luctus augue tristique eu. Donec
      vulputate odio neque, sed semper turpis pellentesque a.
    </p>
  </div>
</template>

<script>
export default {
  name: "ContentDescription",
};
</script>

<style lang="scss" scoped>
.descriptionContainer {
  margin: 0 110px;
  padding: 12px 200px;
  background-color: #efefef;
  text-align: center;
  margin-bottom: 40px;

  @media (max-width: 1024px) {
    padding: 10px 50px;
    text-align: justify;
  }

  @media (max-width: 640px) {
    margin: 16px;
    padding: 12px;
  }

  & h3 {
    text-align: center;
  }
}
</style>
