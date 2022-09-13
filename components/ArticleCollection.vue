<template>
  <div class="article-collection">
    <template v-for="item of collection">
      <nuxt-link :key="item.slug" :to="item.path" class="article-collection__card">
        <div class="article-collection__header">
          <img :src="item.image" :alt="item.title" loading="lazy" />
        </div>
        <div class="article-collection__body">
          <span class="article-collection__category">{{ item.category }}</span>
          <h2 class="article-collection__title">{{ item.title }}</h2>
          <span class="article-collection__author">
            <img :src="item.author.icon" />
            {{ item.author.name }}
          </span>
          <span class="article-collection__date">
            <app-icon icon="calendar" left />
            {{ item.createdAt }}
          </span>
        </div>
      </nuxt-link>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    collection: {
      default: () => [],
      require: true,
      type: Array,
    },
  },
}
</script>