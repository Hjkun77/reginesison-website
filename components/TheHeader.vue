<template>
  <header class="intro">
    <h1 class="intro__hola">
      <span id="typewriter">
        <span class="type-wrap"></span>
      </span>
      <span class="emoji" :style="waveHand"></span>
    </h1>
    <h2 class="intro__motto">
      I'm
      <span class="pangalan">Regine Sison</span>, an undergraduate student from
      the Ateneo de Manila University 🎓, working as product designer, product
      manager and tech & design community leader from Quezon City, Philippines
      🎨
    </h2>
    <h3 class="intro__contact">
      <span>Get in touch</span>
      <span class="emoji pointer" :style="rightPoint"></span>
      <span>
        <a
          href="mailto:regs.mms@gmail.com"
          target="_blank"
          rel="noopener noreferrer"
          class="highlight-link"
          >regs.mms@gmail.com</a
        >
      </span>
    </h3>
  </header>
</template>

<script>
import HandWave from '@/assets/img/icons/waving-hand.png'
import PointRight from '@/assets/img/icons/right-point.png'

export default {
  data() {
    return {
      waveHand: {
        background: `url(${HandWave}) no-repeat center`,
        backgroundSize: '100%',
        marginLeft: '10px'
      },
      rightPoint: {
        background: `url(${PointRight}) no-repeat center`,
        backgroundSize: '100%',
        margin: '0 5px',
        verticalAlign: 'text-bottom'
      },
      element: null,
      toRotate: ['Mabuhay!', 'Hi!', 'こんにちは!', '你好!'],
      period: 2000,
      loopNum: 0,
      txt: '',
      isDeleting: false
    }
  },
  mounted() {
    this.element = document.getElementById('typewriter')
    this.TxtType()
  },
  methods: {
    TxtType() {
      const i = this.loopNum % this.toRotate.length
      const fullTxt = this.toRotate[i]

      if (this.isDeleting) {
        this.txt = fullTxt.substring(0, this.txt.length - 1)
      } else {
        this.txt = fullTxt.substring(0, this.txt.length + 1)
      }
      this.element.innerHTML = '<span class="text-wrap">' + this.txt + '</span>'

      let delta = 200 - Math.random() * 100
      if (this.isDeleting) {
        delta /= 2
      }
      if (!this.isDeleting && this.txt === fullTxt) {
        delta = this.period
        this.isDeleting = true
      } else if (this.isDeleting && this.txt === '') {
        this.isDeleting = false
        this.loopNum++
        delta = 500
      }
      setTimeout(() => {
        this.TxtType()
      }, delta)
    }
  }
}
</script>

<style lang="scss">
@import '../assets/css/styles.scss';

#typewriter > .text-wrap {
  border-right: 0.08em solid $dark-grey;
}

.intro {
  padding: 120px 100px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  max-width: 1440px;
  margin: 0 auto;
  @include weird-medium {
    padding: 120px 70px;
  }
  @include phablet {
    padding: 120px 50px;
  }
  @include mobile {
    padding: 70px 50px;
  }

  &__hola,
  &__motto {
    font-size: 2.5rem;
    @include desktop {
      font-size: 2.25rem;
    }
    @include tablet {
      font-size: 2rem;
    }
    @include phablet {
      font-size: 1.75rem;
    }
    @include small-mobile {
      font-size: 1.5rem;
    }
    @include tiny-mobile {
      font-size: 1.4rem;
    }
    .emoji {
      width: 40px;
      height: 40px;
      @include desktop {
        width: 35px;
        height: 35px;
      }
      @include tablet {
        width: 30px;
        height: 30px;
      }
      @include small-mobile {
        width: 25px;
        height: 25px;
      }
    }
  }
  &__hola {
    font-weight: 300;
  }
  &__motto {
    font-weight: 300;
    max-width: 800px;
    .pangalan {
      font-weight: 700;
    }
  }
  &__contact {
    font-size: 1.25rem;
    font-weight: 400;
    @include phablet {
      font-size: 1rem;
    }
    .emoji {
      &.pointer {
        width: 30px;
        height: 30px;
        margin: 0 5px;
        vertical-align: text-bottom;
        @include phablet {
          width: 25px;
          height: 25px;
        }
      }
    }
    .highlight-link {
      @include transition;
      font-weight: 400;
      text-decoration: none;
      display: inline-block;
      padding: 2px 3px;
      text-decoration: none;
      box-shadow: inset 0 -3px 0 $blue;
      &:hover {
        box-shadow: inset 0 -33px 0 0 $blue;
        color: $white;
      }
    }
  }
}
</style>
