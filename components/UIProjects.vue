<template>
  <section id="featured-projects" class="section">
    <div class="section__title">User Experience and Interface Design</div>
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
          title: 'Virtivent',
          desc:
            'In a summer boot camp, I taught some UX/UI fundamentals to beginners in the field. Virtivent is a made-up application used to demonstrate the user research process.',
          link: "https://www.notion.so/Virtivent-c85412ccc8e64c98ae6600e430194305",
          img: UXUI5,
          tools: ['Figma', 'Notion',]
        },
        {
          title: 'COVID19 Diagnostic App',
          desc:
            'This is a Google Solutions Challenge entry, where the team decided to create a mobile app to help identify potential CoVID-19 cases.',
          link: null,
          img: UXUI1,
          tools: ['Figma']
        },
        {
          title: 'Frontendback Website',
          desc:
            'I am in the process of creating an online startup design studio along with my collaborator. This is the user interface of our soon-to-launch website.',
          link: null,
          img: UXUI2,
          tools: ['Figma']
        },
        {
          title: 'Daily UI',
          desc:
            'This is one of the challenges sent by Daily UI where I was tasked to design a sign-up page.',
          link: null,
          img: UXUI3,
          tools: ['Figma']
        },
        {
          title: 'SeeTurtles',
          desc:
            'This is a self-initiated landing page created specifically to advertise a campaign. ',
          link: null,
          img: UXUI4,
          tools: ['Figma']
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
