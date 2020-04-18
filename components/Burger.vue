<template>
  <button class="burger" >
    <span></span>
  </button>
</template>

<script>
export default {
  methods: {
    toggleActive() {
      this.$refs.burger.classList.toggle('burger--active');
      this.$refs.dropdown.classList.toggle('page-header__inner--opened');
    }
  }

}
</script>

<style lang="scss">
.burger {
  position: relative;
  display: flex;
  width: 38px;
  height: 26px;
  padding: 0;
  background-color: transparent;
  border: none;
  cursor: pointer;

  &::before,
  &::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 4px;
    background-color: $white;
    transition: top 0.25s ease-in-out 0.25s, transform 0.25s ease-in-out;
  }

  &::after {
    top: calc(100% - 4px);
  }

  span {
    width: 100%;
    height: 4px;
    margin: 0 auto;
    background-color: $white;
    transition: width 0.25s ease-in-out 0.25s;
  }

  &--active {
    &::before,
    &::after {
      top: calc(50% - 2px);
      transition: top 0.25s ease-in-out, transform 0.25s ease-in-out 0.25s;
    }

    &::before {
      transform: rotate(45deg);
    }

    &::after {
      transform: rotate(135deg);
    }

    span {
      width: 0;
      transition: width 0.25s ease-in-out;
    }
  }
}
</style>
