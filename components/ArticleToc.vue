<template>
  <div class="article-toc">
    <header class="article-toc__header" @click="toggleState">
      <span>目录</span>
      <app-icon :icon="tocState ? 'arrow-up-drop-circle' : 'arrow-down-drop-circle'" />
    </header>
    <div :class="{ 'article-toc__body': true, 'is-show': tocState }">
      <ul class="article-toc__list">
        <li v-for="link of article.toc" :key="link.id" :class="{
          'article-toc__item': true,
          'article-toc__item--toc2': link.depth === 2,
          'article-toc__item--toc3': link.depth === 3,
        }">
          <a class="article-toc__link" :href="`#${link.id}`" @click.prevent="scrollSmooth('#' + link.id)">
            {{ link.text }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import VueScrollTo from 'vue-scrollto'
export default {
  props: {
    article: {
      default: () => { },
      required: true,
      type: Object,
    },
  },
  data () {
    return {
      tocState: false,
    }
  },
  methods: {
    scrollSmooth (to) {
      const cancelScroll = VueScrollTo.scrollTo(to, 200, { offset: -88 })
      return cancelScroll
    },
    toggleState () {
      this.tocState = !this.tocState
    },
  },
}
</script>
<style>
.article-toc__header {
  padding: 8px 16px;
  font-weight: 700;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  background-color: #dadada;
  width: 320px;
}

.mdi-arrow-up-drop-circle::before {
  content: "▲";
}

.mdi-arrow-down-drop-circle::before {
  content: "▼";
}

.mdi:before,
.mdi-set {
  display: inline-block;
  font: normal normal normal 24px/1 "Material Design Icons";
  font-size: inherit;
  text-rendering: auto;
  line-height: inherit;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.app-icon {
  display: inline-flex;
  line-height: 1;
}

.article-toc__body.is-show {
  max-height: none;
}

.article-toc__body {
  max-height: 0;
  overflow: hidden;
}

.article-toc__list {
  padding: 8px 24px 24px;
  font-size: 13px;
  line-height: 1.25;
  list-style: none;
  border-left: 4px solid #dadada;
}

.article-toc__item {
  padding: 8px 0 0;
}
</style>