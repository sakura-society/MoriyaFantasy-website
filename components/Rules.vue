<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="relative bg-gray-800">
    <div class="
        h-56
        bg-red-600
        sm:h-72
        md:absolute md:left-0 md:h-full md:w-1/2
      ">
      <img class="object-cover w-full h-full" src="~/assets/img/minecraft-bookshelf.jpg" alt="" />
    </div>
    <div class="relative px-4 py-12 mx-auto max-w-7xl sm:px-6 lg:px-8 lg:py-16">
      <div class="md:ml-auto md:w-1/2 md:pl-10">
        <h2 class="text-base font-semibold tracking-wider text-gray-300 uppercase">
          {{ $t('rules.header') }}
        </h2>
        <p class="
            mt-2
            text-3xl
            font-extrabold
            tracking-tight
            text-white
            sm:text-4xl
          ">
          {{ $t('rules.title') }}
        </p>
        <p class="mt-3 text-lg text-gray-300">
          {{ $t('rules.body') }}
        </p>
        <div class="mt-8">
          <div class="inline-flex rounded-md shadow">
            <nuxt-link class="
                inline-flex
                items-center
                justify-center
                px-5
                py-3
                text-base
                font-medium
                text-gray-900
                bg-white
                border border-transparent
                rounded-md
                hover:bg-gray-50
              " :to="localePath('Rules')">
              {{ $t('rules.button') }}
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>
