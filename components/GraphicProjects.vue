<template>
  <section id="featured-projects" class="section">
    <div class="section__title">Graphic Design</div>
    <div class="section__content">
      <div v-for="p in graphicDesign" :key="p.title" class="project">
        <figure class="project__pic">
          <a :href="p.link" target="_blank">
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
              >{{ p.title }}</a
            >
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
import GD1 from '@/assets/img/projects/Graphic Design/1.png'
import GD2 from '@/assets/img/projects/Graphic Design/2.png'
import GD3 from '@/assets/img/projects/Graphic Design/3.png'
import GD4 from '@/assets/img/projects/Graphic Design/4.png'
import GD5 from '@/assets/img/projects/Graphic Design/5.png'
import GD6 from '@/assets/img/projects/Graphic Design/6.png'

export default {
  data() {
    return {
      graphicDesign: [
        {
          title: 'Growing Paths',
          desc:
            'This is a highschool project where I was tasked to create an artwork in the style of the Symbolism Art Movement.',
          link: null,
          img: GD1,
          tools: ['Illustrator Draw', 'Photoshop Draw']
        },
        {
          title: 'Stop Air Pollution',
          desc:
            'This is an advocacy to stop further pollution in the atmosphere.',
          link: null,
          img: GD2,
          tools: ['Illustrator Draw', 'Photoshop Draw']
        },
        {
          title: 'Liquid Galaxy Shirt Design',
          desc:
            'I was tasked to create a put-in-a-shirt drawing for the Google Code-In competition.',
          link: null,
          img: GD3,
          tools: ['Photoshop', 'Tayasui Sketches']
        },
        {
          title: 'G_ Members',
          desc:
            'The goal of this project is create icons representing every member of "G_", which is a small team that holds gatherings for the youth.',
          link: null,
          img: GD4,
          tools: ['Illustrator', 'Photoshop', 'Illustrator Draw']
        },
        {
          title: 'Time',
          desc:
            'This is one of the quotes posted in the social media of Mosaic, to inspire and remind others to live their life to the fullest.',
          link: null,
          img: GD5,
          tools: ['Illustrator']
        },
        {
          title: 'Glass Planet',
          desc:
            'This is a self-initiated work that I created to enhance my skill.',
          link: null,
          img: GD6,
          tools: ['Illustrator']
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
