<template>
  <span :class="classes"></span>
</template>

<script>
export default {
  props: {
    icon: {
      default: '',
      type: String,
    },
    left: {
      default: false,
      type: Boolean,
    },
    right: {
      default: false,
      type: Boolean,
    },
  },
  computed: {
    classes () {
      const icon = this.icon
      return {
        mdi: true,
        'app-icon': true,
        'iconfont': true,
        'app-icon--left': this.left,
        'app-icon--right': this.right,
        [`mdi-${icon}`]: icon,
      }
    },
  },
}
</script>
