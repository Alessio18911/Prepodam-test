<template>
  <div class="page-header">
    <div class="center page-header__wrapper">
      <span class="page-header__city">{{ contacts.city }}</span>
      <Logo class="page-header__logo" />
      <a class="page-header__phone link" :href="`tel:${contacts.phoneNumber}`">{{ contacts.phone }}</a>

      <div class="page-header__inner" ref="dropdown">
        <ul class="page-header__nav main-nav list">
          <li class="main-nav__item" v-for="(item, i) in mainNav" :key="i">
            <a :href="item.href" class="main-nav__item-link link">{{ item.text }}</a>
          </li>
        </ul>
        <ul class="page-header__auth list">
          <li class="page-header__auth-item" v-for="(item, i) in user" :key="i">
            <a :href="item.href" class="page-header__auth-link link">{{ item.text }}</a>
          </li>
        </ul>
        <a class="page-header__btn button button--transparent link" :href="btn.href">{{ btn.text }}</a>
      </div>

      <Burger />
    </div>
  </div>
</template>

<script>
import Logo from '@/components/Logo';
import Burger from '@/components/Burger';

export default {
  data() {
    return {
      contacts: {
        city: "Москва",
        phone: "+7 800-562-345",
        phoneNumber: "+7800562345"
      },

      mainNav: [
        {
          href: "#",
          text: "О проекте"
        },
        {
          href: "#",
          text: "Онлайн-курсы"
        },
        {
          href: "#",
          text: "Статьи"
        }
      ],

      user: [
        {
          href: "#",
          text: "Регистрация"
        },
        {
          href: "#",
          text: "Вход"
        }
      ],

      btn: {
        href: "#",
        text: "Преподавателям"
      }
    };
  },

  components: {
    Logo,
    Burger
  }
};
</script>

<style lang="scss">
.page-header {
  position: relative;
  font-size: 16px;
  padding: 10px 30px 0 22px;
  background-color: $black1;

  .link {
    color: inherit;
  }

  &__wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__city {
    font-size: 14px;
  }

  &__phone.link {
    display: none;
  }

  &__inner {
    position: absolute;
    width: 100%;
    max-height: 0;
    top: 0;
    left: 0;
    text-align: center;
    background: $black1;
    overflow: hidden;

    &__inner--opened {
      max-height: 500px;
    }
  }

  &__logo {
    position: relative;
    z-index: 1;
    margin-right: 4%;
  }

  .main-nav {
    position: relative;
    padding: 124px 0 18px;

    &::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 50%;
      width: 95%;
      height: 1px;
      background-color: $grey2;
      transform: translateX(-50%);
    }
  }

  .main-nav__item {
    padding: 16px 0;
  }

  &__auth.list {
    padding: 13px 0 6px;
  }

  &__auth-item {
    padding: 14px 0;
  }

  &__btn {
    margin-bottom: 32px;
  }
}
</style>
