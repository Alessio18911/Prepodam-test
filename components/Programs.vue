<template>
  <section class="programs">
      <h2 class="programs__title title">{{ title }}</h2>
      <ul class="programs__list list">
        <li class="programs__list-item" v-for="(program, i) in programs" :key="i" :style="{ backgroundImage: ' url(' + require(`assets/images/${ program.image }`) + ')' }">
          <a href="program.link" class="programs__list-link">
            <span>{{ program.name }}</span>
            <span>{{ details }}</span>
          </a>
        </li>
      </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: "Выберите свою программу",
      programs: [
        {
          link: "#",
          image: "school.png",
          name: "Школьная программа"
        },
        {
          link: "#",
          image: "student.png",
          name: "Студенческая программа"
        },
        {
          link: "#",
          image: "postgraduate.png",
          name: "Дополнительное образование"
        }
      ],

      details: "Подробнее о программе"
    }
  }
}
</script>

<style lang="scss">
.programs {
  padding: 57px 0 170px;

  &__title {
    margin: 0 0 46px;
    font-size: 16px;
    font-weight: 500;
    color: $blue1;
    letter-spacing: 0.3px;
    text-align: center;
    text-transform: uppercase;
  }

  &__list {
    display: flex;
    overflow-x: scroll;
  }

  &__list-item {
    flex-shrink: 0;
    width: 238px;
    height: 412px;
    margin: 0 15px;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    overflow: hidden;

    &:hover {
      .programs__list-link {
        transform: translateY(-100px);
      }
    }
  }

  &__list-link {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    height: 512px;
    padding: 27px 0;
    font-size: 18px;
    font-weight: 500;
    color: inherit;
    text-align: center;
    transform: translateY(312px);
    text-decoration: none;
    transition: transform 0.25s ease-in-out;

    &::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba($black1, 0.3);
    }

    span {
      position: relative;
      width: 200px;
    }
  }
}
</style>
