<template>
  <div class="mx-auto max-w-7xl">
    <Navbar />
    <div class="bg-white">
      <div class="px-4 py-16 mx-auto max-w-7xl sm:py-24 sm:px-6 lg:px-8">
        <h2 class="text-3xl font-extrabold text-center text-gray-900">
          {{ $t('rules.header') }}
        </h2>
        <div class="mt-12">
          <dl class="
              space-y-10
              md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-12
              lg:grid-cols-3
            ">
            <div v-for="rule in rules" :key="rule.id">
              <dt class="text-lg font-medium leading-6 text-gray-900">
                {{ rule.id }}. {{ rule.title }}
              </dt>
              <dd class="mt-2 text-base text-gray-500 whitespace-pre-line">
                {{ rule.body }}
              </dd>
            </div>
            <p class="text-sm text-gray-500 border-t border-gray-300 pt-7">
              {{ $t('rules.disclaimer') }}
            </p>
          </dl>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
export default {
  nuxtI18n: {
    paths: {
      // cn: '/rules',
    },
  },
  data () {
    return {
      rules: [
        {
          id: 1,
          title: this.$i18n.t('rules.items[0].title'),
          body: this.$i18n.t('rules.items[0].body'),
        },
        {
          id: 2,
          title: this.$i18n.t('rules.items[1].title'),
          body: this.$i18n.t('rules.items[1].body'),
        },
        {
          id: 3,
          title: this.$i18n.t('rules.items[2].title'),
          body: this.$i18n.t('rules.items[2].body'),
        },

        {
          id: 4,
          title: this.$i18n.t('rules.items[3].title'),
          body: this.$i18n.t('rules.items[3].body'),
        },
        {
          id: 5,
          title: this.$i18n.t('rules.items[4].title'),
          body: this.$i18n.t('rules.items[4].body'),
        },
        {
          id: 6,
          title: this.$i18n.t('rules.items[5].title'),
          body: this.$i18n.t('rules.items[5].body'),
        },
      ],
    }
  },
}
</script>

<style scoped>
</style>
