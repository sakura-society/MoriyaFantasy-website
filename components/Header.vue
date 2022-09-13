<template>
  <div class="relative overflow-hidden bg-white">
    <div class="mx-auto max-w-7xl">
      <div class="
          relative
          z-10
          pb-8
          bg-white
          sm:pb-16
          md:pb-20
          lg:max-w-2xl lg:w-full lg:pb-28
          xl:pb-32
        ">
        <svg class="
            absolute
            inset-y-0
            right-0
            hidden
            w-48
            h-full
            text-white
            transform
            translate-x-1/2
            lg:block
          " fill="currentColor" viewBox="0 0 100 100" preserveAspectRatio="none" aria-hidden="true">
          <polygon points="50,0 100,0 50,100 0,100" />
        </svg>

        <Navbar />

        <main class="
            px-4
            mx-auto
            mt-10
            max-w-7xl
            sm:mt-12 sm:px-6
            md:mt-16
            lg:mt-20 lg:px-8
            xl:mt-28
          ">
          <div class="sm:text-center lg:text-left">
            <h1 class="
                text-4xl
                font-extrabold
                tracking-tight
                text-gray-900
                sm:text-5xl
                md:text-6xl
              ">
              <span class="block text-red-600 xl:inline">守矢幻想</span>
              <span class="block xl:inline"> {{ $t('title') }} </span>
            </h1>
            <p class="
                mt-3
                text-base text-gray-500
                sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto
                md:mt-5 md:text-xl
                lg:mx-0
              ">
              {{ $t('header') }}
            </p>
            <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
              <div class="rounded-md shadow">
                <a href="https://jq.qq.com/?_wv=1027&k=nzNIiTJR" class="
                    flex
                    items-center
                    justify-center
                    w-full
                    px-8
                    py-3
                    text-base
                    font-medium
                    text-white
                    bg-red-600
                    border border-transparent
                    rounded-md
                    hover:bg-red-700
                    md:py-4 md:text-lg md:px-10
                  ">
                  QQ Group
                  <icon-external-link class="w-5 h-5 ml-3 -mr-1" aria-hidden="true" />
                </a>
              </div>
              <div class="mt-3 sm:mt-0 sm:ml-3">
                <a href="#features" class="
                    flex
                    items-center
                    justify-center
                    w-full
                    px-8
                    py-3
                    text-base
                    font-medium
                    text-red-700
                    bg-red-100
                    border border-transparent
                    rounded-md
                    hover:bg-red-200
                    md:py-4 md:text-lg md:px-10
                  ">
                  {{ $t('continue') }}
                </a>
              </div>
            </div>
          </div>
        </main>
      </div>
    </div>
    <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
      <img class="object-cover w-full h-56 sm:h-72 md:h-96 lg:w-full lg:h-full" src="~/assets/img/main_min.png"
        alt="" />
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>

</style>
