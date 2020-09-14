<template>
  <section id="experience" class="section">
    <div class="section__title">Experience</div>
    <div class="section__content">
      <div class="trabajos">
        <div v-for="trabaho in trabahos" :key="trabaho.saan" class="trabajo">
          <div class="saan-kelan">
            <div class="trabajo__saan">
              <a
                :href="trabaho.url"
                target="_blank"
                rel="noopener noreferrer"
                class="underline-link"
              >{{ trabaho.saan }}</a>
            </div>
            <div class="trabajo__kelan">{{ trabaho.kelan }}</div>
          </div>
          <div class="trabajo__posisyon">{{ trabaho.posisyon }}</div>
        </div>
      </div>
      <a :href="resume" target="_blank" class="arrow-link">View My Resume</a>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      resume: '../assets/files/resume.pdf',
      trabahos: [
        {
          saan: 'Create that App! Summer Bootcamp',
          kelan: '2020',
          posisyon: 'Design Instructor',
          url:
            'https://www.instagram.com/p/CCdLha5jNPP/?utm_source=ig_web_copy_link'
        },
        {
          saan: 'Google DSC Solutions Challenge',
          kelan: '2020',
          posisyon: 'Mobile App UI Designer',
          url: 'https://events.withgoogle.com/dsc-solution-challenge/'
        },
        {
          saan: 'Google Code-In',
          kelan: '2019',
          posisyon: 'Open Source Contributor',
          url: 'https://codein.withgoogle.com/archive/'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
@import '../assets/css/styles.scss';

.trabajos {
  margin-bottom: 100px;
}

.trabajo {
  margin-bottom: 25px;
  .saan-kelan {
    display: flex;
    justify-content: space-between;
    @include mobile {
      display: block;
    }
  }
  &__saan {
    font-weight: 700;
  }
  &__kelan {
    font-size: 0.9rem;
    @include mobile {
      font-size: 0.8rem;
    }
  }
}

.arrow-link {
  font-size: 1.25rem;
  &:after {
    width: 20px;
    height: 20px;
  }
}
</style>
