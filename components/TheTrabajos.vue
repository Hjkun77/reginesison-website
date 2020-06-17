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
        'https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3ea72991-1f40-47ae-b123-3de9b02f75ad/Resume_Regine_Sison_%281%29.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200617%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200617T063844Z&X-Amz-Expires=86400&X-Amz-Signature=946b651e6f91d0729a31bfc3d1168d2593669ecf7655f3df0db58d50f92455ce&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Resume_Regine%2520Sison%2520%281%29.pdf%22',
      trabahos: [
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
        },
        {
          saan: 'Mosaic, Bread of Life',
          kelan: '2018 - Present',
          posisyon: 'Social Media Artist',
          url: 'https://www.facebook.com/spiritfoodmosaicbgc/'
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
