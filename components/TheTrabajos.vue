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
                >{{ trabaho.saan }}</a
              >
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
      resume:
        'https://infrequent-title-90c.notion.site/Mabuhay-53266b876bae497b88dfc950391c3c25',
      trabahos: [
        {
          saan: 'Google Developer Student Clubs',
          kelan: '2022-2023',
          posisyon: 'Chief Product Officer',
          url: 'https://www.gdscloyola.org/'
        },
        {
          saan: 'User Experience Society',
          kelan: '2022-2023',
          posisyon: 'Vice President for Consultancy',
          url: 'https://uxsociety.org/'
        },
        {
          saan: 'THR1VE',
          kelan: '2023',
          posisyon: 'Technical Directing Head',
          url: 'https://www.instagram.com/bolmakati/'
        },
        {
          saan: 'Sarisuki',
          kelan: '2022',
          posisyon: 'Product Designer',
          url: 'https://sarisuki.com/'
        },
        {
          saan: 'BTYE',
          kelan: '2021-2022',
          posisyon: 'Product Manager',
          url: 'https://www.facebook.com/byteadmu/'
        },
        {
          saan: 'ErudiFi',
          kelan: '2021',
          posisyon: 'User Experience Researcher',
          url: 'https://www.erudifi.com/'
        },
        {
          saan: 'Teemly',
          kelan: '2020-2022',
          posisyon: 'Co-Founder and Chief Product Officer',
          url: 'https://teemly.io/'
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
