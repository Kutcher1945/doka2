<template lang="pug">
  .pre-footer
    .steps.select-none#steps
      .container
        h2.steps__title Как начать играть
        ul.steps__list
          li.step.step_active
            .step__number 1
            .step__dot
              .step__dot-icon
            h6.step__title Зарегистрируйся
            .step__decoration
              img(src="/images/redesign/landing/step-1.png").step__decoration-image.select-none
          li.step
            .step__number 2
            .step__dot
              .step__dot-icon
            h6.step__title Пройди верификацию
            .step__decoration
              img(src="/images/redesign/landing/step-2.png").step__decoration-image.select-none
          li.step
            .step__number 3
            .step__dot
              .step__dot-icon
            h6.step__title Выбери лобби
            .step__decoration
              img(src="/images/redesign/landing/step-3.png").step__decoration-image.select-none
    .modes.select-none
      .container
        h4.modes__title Играй и выигрывай в режимах
        ul.modes__list
          li.mode.mode-1
            svg-icon(name="redesign/mode-1").mode__icon
            | Solo mid 1x1
          li.mode.mode-2
            svg-icon(name="redesign/mode-2").mode__icon
            | All pick
          li.mode.mode-3
            svg-icon(name="redesign/mode-3").mode__icon
            | Captains mode
    .faq
      .container
        h2.faq__title.select-none FAQ
        .faq__content
          FaqAccordion(
            :questions-and-answers="faq"
          ).faq__accordion
          //form.faq__form(
          //  @submit.prevent="sendProposal"
          //)
          //  input(type="text" name="proposal" placeholder="Что еще мы можем улучшить?").faq__input
          //  button.faq__button(type="submit") Отправить
</template>

<script>
import FaqAccordion from '@/components/Landing/FaqAccordion.vue'

export default {
  name: 'LandingPreFooter',
  components: { FaqAccordion },
  data () {
    return {
      faq: [
        {
          title: 'Как пройдет отбор на бета-тест? Как я узнаю, что меня выбрали?',
          text: 'Вы получите уведомление в Телеграме от нашего бота.'
        },
        {
          title: 'Что делать, если в игре я встречу недобросовестного игрока?',
          text: 'Если встретите подозительного игрока, пожалуйтесь на него на нашем сайте в процессе матча или сразу после его завершения. Если окажется, что он мошенничал и использовал читы, деньги за игру вернутся на ваш игровой счет.'
        },
        {
          title: 'Что потребуется для запуска игры?',
          text: 'Потребуется ПК с рекомендованными системными требованиями, хороший интернет и документ, удостоверяющий вашу личность для верификации аккаунта.'
        },
        {
          title: 'Сколько продлится бета-тест? ',
          text: 'Бета-тестирование платформы начнется сразу после набора нужного количества игроков и продлится 2 месяца. Точная дата окончания может измениться.'
        },
        {
          title: 'Что будет входить в мои обязанности?',
          text: 'Вам нужно будет играть, соревноваться, выводить средства на карту, находить лаги в системе и сообщать о них нам.'
        },
        {
          title: 'Что будет после бета-теста?',
          text: 'После бета-тестирования состоится открытый запуск соревновательной платформы CyberT для всех желающих.'
        },
        {
          title: 'Как мне вывести бонусные 200 ₽?',
          text: 'Чтобы вывести бонусные 200 ₽, нужно их удвоить: для этого соревнуйтесь с другими пользователями платформы и выигрывайте матчи.'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

/*
  ============================================================
  Pre-footer
  ============================================================
*/
.pre-footer {
  background-image: url(/images/redesign/landing/background-1.png);
  background-size: 192rem 165.4rem;
  background-repeat: repeat-x;
  background-position: bottom center;
  @media only screen and (max-width: 600px) {
    -webkit-background-size: contain;
    background-size: contain;
  }
}
/*
  ============================================================
  Steps
  ============================================================
*/
.steps {
  margin-bottom: 2.4rem;
  @media only screen and (max-width: 600px) {
    margin-bottom: 0;
    .container {
      background: #000;
    }
  }
}
.steps__title {
  font-family: 'Colus', sans-serif;
  font-weight: 400;
  font-size: 7rem;
  line-height: 124%;
  color: #FFFFFF;
  text-align: center;
  @media only screen and (max-width: 600px) {
    font-size: 48px;
  }
}
.steps__list {
  display: grid;
  grid-template-columns: repeat(3, 25rem);
  grid-gap: 10rem;
  justify-content: center;
  @media only screen and (max-width: 600px) {
    grid-template-columns: auto;
    grid-gap: 0;
  }
}
.step {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.step {
  &_active {
    .step__number {
      color: #FFFFFF;
    }
    .step__dot {
      &-icon {
        background: #9B67CF;
        box-shadow: 0 0 2.5rem #9B67CF;
      }
    }
    .step__title {
      color: #FFFFFF;
      text-shadow: 0 0 2.5rem #9B67CF;
    }
  }
}
.step__number {
  font-family: 'Colus', sans-serif;
  font-size: 7rem;
  line-height: 124%;
  color: #474747;
  text-shadow: 0 0 3.7rem rgba(155, 103, 207, 0.51);

  margin-bottom: .6rem;
  @media only screen and (max-width: 600px) {
    color: #fff;
  }
}
.step__dot {
  width: 100%;
  position: relative;

  margin-bottom: 1.4rem;

  &:after {
    content: '';

    width: calc(100% - 1.6rem - 1.6rem + 10rem);
    height: .2rem;

    position: absolute;
    left: calc(50% + 1.6rem);
    top: 50%;
    transform: translateY(-50%);

    background: #474747;
    @media only screen and (max-width: 600px) {
      content: none;
    }

  }

  &-icon {
    margin: 0 auto;
    width: 1.6rem;
    height: 1.6rem;
    border-radius: 50%;
    background: #474747;
    @media only screen and (max-width: 600px) {
        background: #9B67CF;
        box-shadow: 0 0 2.5rem #9B67CF;
    }
  }
}
.step__title {
  font-family: 'Colus', sans-serif;
  font-size: 2.5rem;
  line-height: 124%;
  text-align: center;

  min-height: 8rem;

  color: #474747;
  text-shadow: 0 0 2.5rem rgba(155, 103, 207, 0.44);

  margin-bottom: 1.2rem;
  @media only screen and (max-width: 600px) {
    color: #fff;
  }
}
.step__decoration {
  &-image {
    width: 24.8rem;
    height: 16.9rem;
  }
}
.step:last-child {
  .step__dot:after {
    display: none;
  }
}
/*
  ============================================================
  Modes
  ============================================================
*/
.modes {
  margin-bottom: 4.8rem;
  @media only screen and (max-width: 600px) {
    margin-bottom: 0;
    .container {
      background: #000;
    }
  }
}
.modes__title {
  font-family: 'Colus', sans-serif;
  font-weight: 400;
  font-size: 2.5rem;
  line-height: 124%;
  text-align: center;
  color: #FFFFFF;

  margin-bottom: 4.8rem;
  @media only screen and (max-width: 600px) {
    padding-top: 100px;
  }
}
.modes__list {
  display: grid;
  grid-template-columns: repeat(3, 28.5rem);
  grid-gap: 6.4rem;
  justify-content: center;
  @media only screen and (max-width: 600px) {
    grid-template-columns: auto;
    grid-gap: 24px;

  }
}
.mode {
  background: #101010;
  box-shadow: 0 .1rem 8.9rem rgba(255, 0, 184, 0.25);
  border-radius: .8rem;

  font-family: 'Colus', sans-serif;
  font-size: 2.5rem;
  line-height: 124%;
  color: #FFFFFF;
  text-align: center;

  position: relative;
  padding: .7rem 3rem .7rem 3rem;
}
.mode__icon {
  width: 8rem;
  height: 10rem;

  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
}
.mode-1 {
  .mode__icon {
    left: -2rem;
  }
}
.mode-2 {
  .mode__icon {
    left: -2rem;
  }
}
.mode-3 {
  .mode__icon {
    left: -4rem;
  }
}
/*
  ============================================================
  FAQ title
  ============================================================
*/
.faq {
  padding-bottom: 13.5rem;
}
.faq__title {
  font-family: 'Colus', sans-serif;
  font-weight: 400;
  font-size: 12rem;
  line-height: 125%;
  color: #FFFFFF;

  text-align: center;

  margin-bottom: 1rem;
  @media only screen and (max-width: 600px) {
    padding-top: 100px;
    font-size: 48px;
  }
}
.faq__content {
  max-width: 100rem;
  margin: 0 auto;

  background: rgba(13, 13, 13, 0.75);
  backdrop-filter: blur(1rem);
  border-radius: 1.4rem;

  padding: 2.4rem 3.2rem;
}
.faq__accordion {
  //margin-bottom: 1.6rem;
}
.faq__form {
  display: flex;
  align-items: center;
}
.faq__input {
  flex-grow: 1;
  outline: none;

  background: rgba(217, 217, 217, 0.12);
  border: none;
  padding: .8rem 1.2rem;

  font-size: 2.3rem;
  line-height: 121%;

  color: #FFFFFF;
  &::placeholder {
    color: #B7B7B7;
  }
}
.faq__button {
  flex: 0 0 auto;

  background: linear-gradient(280.78deg, #5F0000 -33.58%, #DB9919 102.08%), rgba(217, 217, 217, 0.12);
  border: none;
  padding: .8rem 1.2rem;

  font-size: 2.3rem;
  line-height: 121%;
  color: #FFFFFF;

  margin-left: 1.6rem;
}
</style>
