<template>
  <footer class="article-footer">
    <div class="article-footer__author">
      <img class="article-footer__author-image" :src="_author.icon" />
      <div class="article-footer__author-name">
        {{ _author.name }}
      </div>
      <div class="article-footer__author-bio">{{ _author.bio }}</div>
    </div>
    <div class="article-footer__meta">
      <article-meta-item icon="calendar" :text="'公開日：' + createdAt" />
      <article-meta-item icon="update" :text="'更新日：' + updatedAt" />
    </div>
  </footer>
</template>

<script>
export default {
  props: {
    author: {
      default: () => { },
      required: true,
      type: Object,
    },
    createdAt: {
      default: '',
      type: String,
    },
    updatedAt: {
      default: '',
      required: true,
      type: String,
    },
  },
  computed: {
    _author () {
      const author = { ...this.author }
      return {
        name: author.name ? author.name : '',
        bio: author.bio ? author.bio : '',
        icon: author.uuid
          ? 'https://crafatar.com/avatars/' + author.uuid + '?overlay=true'
          : '',
      }
    },
  },
}
</script>