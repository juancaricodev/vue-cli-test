<template>
  <div class="about">
    <h1>This is an about page</h1>
    <section class="about__navbar">
      <div class="about__navbar-item"></div>
      <div class="about__navbar-item"></div>
      <div class="about__navbar-item"></div>
    </section>
  </div>
</template>

<style lang="scss">
.about {
  width: 100%;
  background-color: aquamarine;

  &__navbar {
    border: solid 3px blue;
    display: grid;
    grid-template-columns: repeat(3, 1fr);

    &-item {
      width: 100%;
      height: 200px;
      border: solid 1px red;
      background-color: cornflowerblue;
    }

  }
}
</style>
