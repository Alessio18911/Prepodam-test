<template>
  <section class="header-block">
    <div class="center">
      <h1 class="header-block__title title" v-html="title"></h1>
      <p class="header-block__description text">{{ description }}</p>
      <button class="button button--pink" type="button">{{ button }}</button>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: "<span>Первая</span> образовательная онлайн-платформа, созданная преподами!",
      description: "Описание уникального торгового предложения или же описание названия того или иного продукта, который на первом экран",
      button: "зарегистрироваться"
    }
  }
}
</script>

<style lang="scss">
.header-block {
  padding: 153px 0 61px;
  text-align: center;
  background: url('~assets/images/bg320.png') no-repeat center;
  background-size: cover;

  &__title {
    margin: 0 0 43px;
    font-size: 20px;
    letter-spacing: 0.4px;

    span {
      color: $pink;
    }
  }

  &__description {
    margin: 0 0 66px;
    font-family: 'Open Sans', Arial, sans-serif;
    font-size: 12px;
    line-height: 1.33;
  }
}
</style>
