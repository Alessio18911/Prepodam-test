<template>
  <a class="logo" :href="link">
    <img :src="require(`assets/images/${src}`)" width="111" height="111" :alt="alt" />
  </a>
</template>

<script>
export default {
  data() {
    return {
      link: "#",
      src: "logo.png",
      alt: "Logo"
    }
  }
}
</script>

<style lang="scss">
.logo {
  img {
    width: 88px;
    height: 88px;
  }
}
</style>
