<template>
  <div class="bg-gray-50">
    <Navbar class="bg-white" />
    <div class="mx-auto max-w-7xl py-16">
      <article class="flex flex-col items-start justify-center max-w-4xl mx-auto mb-16 shadow bg-white rounded-lg">
        <article-header :title="_article.title" :image="_article.image" :meta="meta"
          class="px-4 py-16 mx-auto max-w-7xl sm:px-6 lg:px-8" />
        <div class="mt-12">
          <article-toc :article="_article" />
          <article-body :article="_article" />
        </div>
      </article>
    </div>
    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params, error }) {
    const { category, slug } = params
    let article
    try {
      try {
        article = await $content(category, slug).fetch()
      } catch (e) {
        throw new Error('Page not found.')
      }
    } catch (e) {
      if (e.message === 'Page not found.') {
        error({ statusCode: 404, message: e.message })
      } else {
        error({ statusCode: 500, message: e.message })
      }
    }
    return {
      article
    }
  },
  head () {
    const article = this.article
    const meta = []
    if (article.description) {
      if (article.description.length > 80) {
        article.description = (
          article.description.substr(0, 80) + '...'
        ).replace(/\r?\n/g, '')
      }
      meta.push({
        hid: 'description',
        name: 'description',
        content: article.description,
      })
      meta.push({
        hid: 'og:description',
        property: 'og:description',
        content: article.description,
      })
    }
    if (article.title) {
      meta.push({
        hid: 'og:title',
        property: 'og:title',
        content: article.title,
      })
    }
    if (article.path) {
      meta.push({
        hid: 'og:url',
        property: 'og:url',
        content: this.$config.baseUrl + article.path,
      })
    }
    if (article.image) {
      meta.push({
        hid: 'og:image',
        property: 'og:image',
        content: article.image,
      })
    }
    return {
      title: this._article.title,
      meta,
    }
  },
  computed: {
    // Article
    _article () {
      const article = { ...this.article }
      if (article.createdAt) {
        const createdAt = new Date(article.createdAt)
        article.createdAt =
          createdAt.getFullYear() +
          '-' +
          ('0' + (createdAt.getMonth() + 1)).slice(-2) +
          '-' +
          ('0' + createdAt.getDate()).slice(-2)
      }
      if (article.updatedAt) {
        const updatedAt = new Date(article.updatedAt)
        article.updatedAt =
          updatedAt.getFullYear() +
          '-' +
          ('0' + (updatedAt.getMonth() + 1)).slice(-2) +
          '-' +
          ('0' + updatedAt.getDate()).slice(-2)
      }
      if (!article.image) {
        article.image = ''
      }
      return article
    },
    // Breadcrumbs items
    breadcrumbs () {
      return [
        {
          disabled: false,
          to: '/',
          text: 'ホーム',
        },
        {
          disabled: true,
          to: this._article.path,
          text: this._article.title,
        },
      ]
    },
    // Meta to display in article header
    meta () {
      const article = { ...this._article }
      const meta = []
      if (article.createdAt) {
        meta.push({
          icon: 'calendar',
          text: article.createdAt,
        })
      }
      if (article.updatedAt) {
        meta.push({
          icon: 'update',
          text: article.updatedAt,
        })
      }
      return meta
    },
  },
}
</script>