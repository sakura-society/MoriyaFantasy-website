<template>
  <div class="flex items-center">
    <component :is="textTag" v-bind="textAttributes" class="ml-2 text-sm text-gray-700 dark:text-gray-300">
      {{ text }}
    </component>
  </div>
</template>

<script>
import AppIcon from '@/components/AppIcon'
export default {
  components: {
    AppIcon,
  },
  props: {
    text: {
      default: '',
      required: true,
      type: String,
    },
    href: {
      default: '',
      type: String,
    },
    to: {
      default: '',
      type: String,
    },
  },
  computed: {
    textTag () {
      const tag = this.href ? 'a' : this.to ? 'nuxt-link' : 'span'
      return tag
    },
    textAttributes () {
      const attributes = {}
      const href = this.href
      const to = this.to
      if (href) {
        attributes.href = href
      }
      if (to) {
        attributes.to = to
      }
      return attributes
    },
  },
}
</script>