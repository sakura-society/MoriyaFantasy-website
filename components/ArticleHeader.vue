<template>
  <header class="article-header">
    <h1 class="mb-4 text-3xl font-bold tracking-tight text-black md:text-5xl dark:text-white">{{ title }}</h1>
    <div v-if="meta.length" class="flex mb-4 text-gray-600 dark:text-gray-400">
      创建/修改日期:
      <template v-for="item in _meta">
        <article-meta-item :key="item.id" :icon="item.icon" :image="item.image" :text="item.text" :to="item.to"
          :href="item.href" />
      </template>
    </div>
    <div v-if="image" class="rounded-lg shadow-md">
      <img :src="image" :alt="title" loading="lazy" class="rounded-lg shadow-md" />
    </div>
    <p v-if="_description" class="article-header__description">
      {{ _description }}
    </p>
  </header>
</template>

<script>
export default {
  props: {
    title: {
      default: '',
      required: true,
      type: String,
    },
    description: {
      default: '',
      type: String,
    },
    image: {
      default: '',
      type: String,
    },
    meta: {
      default: () => [],
      type: Array,
    },
  },
  computed: {
    _meta () {
      return this.meta.map((item, index) => {
        item.id = index + 1
        return item
      })
    },
    _description () {
      let description = this.description
      if (this.meta.length || this.image) {
        description = ''
      }
      return description
    },
  },
}
</script>