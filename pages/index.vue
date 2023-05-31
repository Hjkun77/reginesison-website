<template>
  <div class="portfolio">
    <toggle-wrap />
    <the-header />
    <the-background />
    <the-talent />
    <the-trabajos />
    <UI-projects />
    <!-- <featured-projects /> -->
    <graphic-projects />
    <!-- <other-projects /> -->
    <the-footer />
    <button
      id="launch-top"
      @mouseenter="hovered = true"
      @mouseleave="hovered = false"
      @click="scrollTop()"
    >
      <img :src="rocketLauncher" />
    </button>
  </div>
</template>

<script>
import ToggleWrap from '@/components/ToggleWrap.vue'
import TheHeader from '@/components/TheHeader.vue'
import TheBackground from '@/components/TheBackground.vue'
import TheTalent from '@/components/TheTalent.vue'
import TheTrabajos from '@/components/TheTrabajos.vue'
// import FeaturedProjects from '@/components/FeaturedProjects.vue'
// import GraphicProjects from '@/components/GraphicProjects.vue'
import UIProjects from '@/components/UIProjects.vue'
// import OtherProjects from '@/components/OtherProjects.vue'
import TheFooter from '@/components/TheFooter.vue'
import Rocket1 from '@/assets/img/icons/rocket-1.png'
import Rocket2 from '@/assets/img/icons/rocket-2.png'
import Cover from '@/assets/img/Cover.png'

export default {
  components: {
    ToggleWrap,
    TheHeader,
    // GraphicProjects,
    UIProjects,
    TheBackground,
    TheTalent,
    TheTrabajos,
    // FeaturedProjects,
    // OtherProjects,
    TheFooter
  },
  data() {
    return {
      myRocket: null,
      hovered: false,
      title: 'Regine Sison | Product Designer',
      desc:
        "I'm Regine Sison, an undegraduate student from the Ateneo de Manila University 🎓 working as product designer, product manager and tech & design community leader from Quezon City, Philippines 🎨",
      img: Cover,
      url: '',
      siteName: 'Regine Sison | Product Designer'
    }
  },
  computed: {
    rocketLauncher() {
      return this.hovered ? Rocket2 : Rocket1
    }
  },
  mounted() {
    this.myRocket = document.getElementById('launch-top')
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 100) {
        this.myRocket.style.display = 'block'
      } else {
        this.myRocket.style.display = 'none'
      }
    },
    scrollTop() {
      window.scrollTo({
        top: 0,
        left: 0,
        behavior: 'smooth'
      })
    }
  },
  head() {
    return {
      title: 'Regine Sison',
      meta: [
        {
          property: 'og:type',
          content: 'article'
        },
        {
          property: 'og:description',
          content: this.desc
        },
        {
          property: 'og:image',
          content: this.img
        },
        {
          property: 'og:url',
          content: this.url
        },
        {
          property: 'og:site_name',
          content: this.siteName
        },
        {
          name: 'twitter:title',
          content: this.title
        },
        {
          name: 'twitter:description',
          content: this.desc
        },
        {
          name: 'twitter:image',
          content: this.img
        },
        {
          name: 'twitter:card',
          content: 'summary_large_image'
        },
        {
          name: 'robots',
          content: 'index,follow'
        }
      ]
    }
  }
}
</script>
