<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="py-12 bg-white">
    <div class="px-4 mx-auto max-w-7xl sm:px-6 lg:px-8">
      <div class="lg:text-center">
        <h2 id="features" class="
            text-base
            font-semibold
            tracking-wide
            text-red-600
            uppercase
          ">
          {{ $t('features.title') }}
        </h2>
        <p class="
            mt-2
            text-3xl
            font-extrabold
            leading-8
            tracking-tight
            text-gray-900
            sm:text-4xl
          ">
          {{ $t('features.header') }}
        </p>
        <p class="max-w-2xl mt-4 text-xl text-gray-500 lg:mx-auto"></p>
      </div>

      <div class="mt-10">
        <dl class="
            space-y-10
            md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-10
          ">
          <div v-for="feature in features" :key="feature.name" class="relative">
            <dt>
              <div class="
                  absolute
                  flex
                  items-center
                  justify-center
                  w-12
                  h-12
                  text-white
                  bg-red-500
                  rounded-md
                ">
                <component :is="feature.icon" class="w-6 h-6" aria-hidden="true" />
              </div>
              <p class="ml-16 text-lg font-medium leading-6 text-gray-900">
                {{ $t(feature.name) }}
              </p>
            </dt>
            <dd class="mt-2 ml-16 text-base text-gray-500">
              {{ $t(feature.description) }}
            </dd>
          </div>
        </dl>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      features: [
        {
          name: this.$i18n.t('features.items[0].name'),
          description: this.$i18n.t('features.items[0].description'),
          icon: 'icon-sparkles',
        },
        {
          name: this.$i18n.t('features.items[1].name'),
          description: this.$i18n.t('features.items[1].description'),
          icon: 'icon-scale',
        },
        {
          name: this.$i18n.t('features.items[2].name'),
          description: this.$i18n.t('features.items[2].description'),
          icon: 'icon-chip',
        },
        {
          name: this.$i18n.t('features.items[3].name'),
          description: this.$i18n.t('features.items[3].description'),
          icon: 'icon-emoji-happy',
        },
      ],
    }
  },
}
</script>
