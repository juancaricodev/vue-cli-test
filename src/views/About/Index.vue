<template>
  <div class="about">
    <h1>This is an about page</h1>
    <section class="about__navbar">
      <div
        class="about__navbar-item"
        :style="{ backgroundColor: bgColor }"
        @click="changeColor"
      ></div>
      <div class="about__navbar-item"></div>
      <div class="about__navbar-item"></div>
    </section>
    <!-- <button class="about__btn" @click="changeColor">Change Color</button> -->
  </div>
</template>

<script>
import { reactive, toRefs, computed } from 'vue'
export default {
  setup () {
    const aboutState = reactive({
      colorActive: false,

      bgColor: computed(() => {
        if (aboutState.colorActive === false) {
          return 'papayawhip'
        } else if (aboutState.colorActive === true) {
          return 'cornflowerblue'
        }
      })
    })

    const changeColor = () => {
      aboutState.colorActive = !aboutState.colorActive
    }

    return {
      ...toRefs(aboutState),

      changeColor
    }
  }
}
</script>

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
      /* background-color: cornflowerblue; */
    }
  }
}

/* .active {
  background: papayawhip;
} */
</style>
