<template>
  <section id="featured-projects" class="section">
    <div class="section__title">Featured Works</div>
    <div class="section__content">
      <div v-for="p in uxui" :key="p.title" class="project">
        <figure class="project__pic">
          <a :href="p.link" target="_blank" rel="noopener noreferrer">
            <img :src="p.img" alt />
          </a>
        </figure>
        <figcaption class="project__caption">
          <div class="project__name">
            <a
              :href="p.link"
              target="_blank"
              rel="noopener noreferrer"
              class="underline-link"
            >
              {{ p.title }}
            </a>
          </div>
          <p v-html="p.desc"></p>
          <div class="project__used">
            <span
              v-for="tool in p.tools"
              :key="tool"
              class="project__used__item"
              >{{ tool }}</span
            >
          </div>
        </figcaption>
      </div>
    </div>
  </section>
</template>

<script>
import UXUI1 from '@/assets/img/projects/UI/1.png'
import UXUI2 from '@/assets/img/projects/UI/2.png'
import UXUI3 from '@/assets/img/projects/UI/3.png'
import UXUI4 from '@/assets/img/projects/UI/4.png'
import UXUI5 from '@/assets/img/projects/UI/5.png'

export default {
  data() {
    return {
      uxui: [
        {
          title: 'Sarisuki',
          desc:
            'All daily essentials delivered to you. Providing local communities fresh groceries and everyday needs. Click for more.',
          link:
            'https://infrequent-title-90c.notion.site/SariSuki-Webstore-0fd57f1d58d544d68ff4fb3cb8e2161f',
          img: UXUI1,
          tools: ['Product Design', 'User Research']
        },
        {
          title: 'ErudiFi',
          desc:
            'Making education affordable. Building a better future for youths in Southeast Asia. Click for more.',
          link:
            'https://infrequent-title-90c.notion.site/ErudiFi-1eafaa24f2a34ce397665c2ec68f881e',
          img: UXUI2,
          tools: ['User Research']
        },
        {
          title: 'Teemly',
          desc:
            'All in one scheduling toolkit - manage your meetings better. Click for more.',
          link:
            'https://infrequent-title-90c.notion.site/Teemly-6573bf58769941fab2ffc0a94f081e30',
          img: UXUI3,
          tools: ['Product Design', 'User Research', 'Product Mgt']
        },
        {
          title: 'Pavilion',
          desc:
            'Restructuring the org landscape. Becoming the go-to org platform in the university. Click for more.',
          link:
            'https://infrequent-title-90c.notion.site/Pavilion-8de51603d24a4bfcba77508ae6036186',
          img: UXUI4,
          tools: ['Product Design', 'User Research']
        },
        {
          title: 'Startup Summit',
          desc:
            'Launch your purpose. Blast off into the future as catalysts for change! Click for more.',
          link:
            'https://infrequent-title-90c.notion.site/Startup-Summit-ac804a8bd2a74773a8c17b53725136cc',
          img: UXUI5,
          tools: ['Product Mgt']
        }
      ]
    }
  }
}
</script>

<style lang="scss">
@import '../assets/css/styles.scss';

#featured-projects {
  a:after {
    display: none;
  }
  .project {
    display: flex;
    margin-bottom: 100px;
    margin-left: -5%;
    width: 125%;
    @include thirteen {
      width: 115%;
    }
    @include desktop {
      width: 105%;
    }
    @include tablet {
      width: 100%;
      display: block;
      margin-bottom: 70px;
    }
    &.screentime {
      margin-bottom: 70px;
    }
    &:last-of-type {
      margin-bottom: 0;
    }
    &__pic {
      max-width: 700px;
      overflow: visible;
      margin: 0;
      a {
        display: block;
      }
      &.phones {
        a {
          display: flex;
          justify-content: space-between;
        }
        .phone {
          margin: 0 -7%;
          &:first-of-type {
            margin-left: -5%;
          }
        }
      }
      img {
        width: 100%;
        max-width: 100%;
        vertical-align: bottom;
      }
    }
    &__caption {
      width: 125px;
      flex-shrink: 0;
      margin-left: 30px;
      @include tablet {
        width: 100%;
        margin-top: 25px;
        margin-left: 0;
      }
    }
    &__name {
      margin-bottom: 10px;
      a {
        font-weight: 700;
      }
    }
    &__used {
      &__item {
        display: inline-block;
        margin: 3px 3px 3px 0;
        font-family: 'Inconsolata', monospace;
        font-size: 0.75rem;
        font-weight: 700;
        padding: 2px 7px;
        border-radius: 3px;
        color: $blue;
        border: 1px solid $blue;
        background: transparent;
        &:first-of-type {
          margin-left: 0;
        }
      }
    }
    p {
      font-size: 0.85rem;
      line-height: 1.3;
    }
  }
}
</style>
