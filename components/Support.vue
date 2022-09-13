<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="bg-gray-50">
    <div class="
        px-4
        py-12
        mx-auto
        max-w-7xl
        sm:px-6
        lg:py-16 lg:px-8 lg:flex lg:items-center lg:justify-between
      ">
      <h2 class="text-3xl font-extrabold tracking-tight text-gray-900 sm:text-4xl">
        <span class="block">{{ $t('support.title') }}</span>
        <span class="block text-red-600">{{ $t('support.accent') }}</span>
      </h2>
      <div class="flex mt-8 lg:mt-0 lg:flex-shrink-0">
        <div class="inline-flex rounded-md shadow">
          <a href="https://afdian.net/a/sakura_society" class="
              inline-flex
              items-center
              justify-center
              px-5
              py-3
              text-base
              font-medium
              text-white
              bg-red-600
              border border-transparent
              rounded-md
              hover:bg-red-700
            ">
            {{ $t('support.button') }}
            <icon-external-link class="w-5 h-5 ml-3 -mr-1" aria-hidden="true" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
}
</script>
