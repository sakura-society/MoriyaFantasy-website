<template>
  <div>
    <div class="relative px-4 pt-6 sm:px-6 lg:px-8">
      <nav class="
          relative
          flex
          items-center
          justify-between
          sm:h-10
          lg:justify-start
        " aria-label="Global">
        <div class="flex items-center flex-grow flex-shrink-0 lg:flex-grow-0">
          <div class="flex items-center justify-between w-full md:w-auto">
            <a href="https://mc.sakurakoyi.top">
              <span class="sr-only">守矢幻想</span>
              <img class="w-auto h-10 sm:h-12" src="~/assets/img/touhou-logo.png" />
            </a>
            <div class="flex items-center -mr-2 md:hidden">
              <button type="button" class="
                  inline-flex
                  items-center
                  justify-center
                  p-2
                  text-gray-400
                  bg-white
                  rounded-md
                  hover:text-gray-500 hover:bg-gray-100
                  focus:outline-none
                  focus:ring-2
                  focus:ring-inset
                  focus:ring-red-500
                " aria-expanded="false">
                <span class="sr-only">Open main menu</span>
                <!-- Heroicon name: outline/menu -->
                <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                  stroke="currentColor" aria-hidden="true" @click="menuState = !menuState">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                </svg>
              </button>
            </div>
          </div>
        </div>
        <div class="hidden md:block md:ml-10 md:pr-4 md:space-x-8">
          <nuxt-link class="font-medium text-gray-500 hover:text-gray-900" :to="localePath('/')">
            {{ $t('pages.index') }}
          </nuxt-link>

          <nuxt-link class="font-medium text-gray-500 hover:text-gray-900" :to="localePath('Rules')">
            {{ $t('pages.rules') }}

          </nuxt-link>
          <a href="/server/policies" class="font-medium text-gray-500 hover:text-gray-900">
            {{ $t('pages.policies') }}
          </a>
          <a href="https://jq.qq.com/?_wv=1027&k=nzNIiTJR" class="font-medium text-gray-500 hover:text-gray-900">QQ
            Group
            <icon-external-link class="inline-block w-5 h-5 -mr-1" aria-hidden="true" />
          </a>
          <a href="https://afdian.net/a/sakura_society" class="font-medium text-gray-500 hover:text-gray-900">afdian
            <icon-external-link class="inline-block w-5 h-5 -mr-1" aria-hidden="true" />
          </a>
        </div>
        <!--测试二级导航
        <div class="flex-grow-0 flex-shrink-0 w-[118px] h-64">
          <div
            class="flex flex-col justify-start items-start absolute left-[200px] top-[40px] overflow-hidden rounded-[10px] bg-white"
            style="box-shadow: 0px 3px 6px -4px rgba(0,0,0,0.12), 0px 6px 16px 0 rgba(0,0,0,0.08), 0px 9px 28px 8px rgba(0,0,0,0.05);">
            <div class="flex flex-col justify-start items-start self-stretch flex-grow py-1 bg-white">
              <div class="flex flex-col justify-start items-start self-stretch flex-grow">
                <div
                  class="flex justify-start items-center self-stretch flex-grow-0 flex-shrink-0 relative overflow-hidden gap-2 px-3 py-[5px]">
                  <p class="flex-grow-0 flex-shrink-0 text-sm text-left text-gray-500 hover:text-gray-900">
                    1st menu item
                  </p>
                </div>
                <div
                  class="flex justify-start items-center self-stretch flex-grow-0 flex-shrink-0 relative gap-2 px-3 py-[5px]">
                  <p class="flex-grow-0 flex-shrink-0 text-sm text-left text-gray-500 hover:text-gray-900">
                    2nd menu item
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
        -->
      </nav>
    </div>

    <!--
          Mobile menu, show/hide based on menu open state.

          Entering: "duration-150 ease-out"
            From: "opacity-0 scale-95"
            To: "opacity-100 scale-100"
          Leaving: "duration-100 ease-in"
            From: "opacity-100 scale-100"
            To: "opacity-0 scale-95"
        -->
    <transition enter-active-class="duration-150 ease-out" enter-class="scale-95 opacity-0"
      enter-to-class="scale-100 opacity-100" leave-active-class="duration-100 ease-in"
      leave-class="scale-100 opacity-100" leave-to-class="scale-95 opacity-0">
      <div v-if="menuState" v-on-clickaway="closeMenu" class="
          absolute
          inset-x-0
          top-0
          z-10
          p-2
          transition
          origin-top-right
          transform
          md:hidden
        ">
        <div class="
            overflow-hidden
            bg-white
            rounded-lg
            shadow-md
            ring-1 ring-black ring-opacity-5
          ">
          <div class="flex items-center justify-between px-5 pt-4">
            <div>
              <img class="w-auto h-8" src="~/assets/img/touhou-logo.png" alt="" />
            </div>
            <div class="-mr-2">
              <button type="button" class="
                  inline-flex
                  items-center
                  justify-center
                  p-2
                  text-gray-400
                  bg-white
                  rounded-md
                  hover:text-gray-500 hover:bg-gray-100
                  focus:outline-none
                  focus:ring-2
                  focus:ring-inset
                  focus:ring-red-500
                ">
                <span class="sr-only">Close main menu</span>
                <!-- Heroicon name: outline/x -->
                <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                  stroke="currentColor" aria-hidden="true" @click="menuState = !menuState">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
              </button>
            </div>
          </div>
          <div class="px-2 pt-2 pb-3 space-y-1">
            <nuxt-link class="
                block
                px-3
                py-2
                text-base
                font-medium
                text-gray-700
                rounded-md
                hover:text-gray-900 hover:bg-gray-50
              " :to="localePath('/')">
              {{ $t('pages.index') }}
            </nuxt-link>

            <nuxt-link class="
                block
                px-3
                py-2
                text-base
                font-medium
                text-gray-700
                rounded-md
                hover:text-gray-900 hover:bg-gray-50
              " :to="localePath('Rules')">
              {{ $t('pages.rules') }}
            </nuxt-link>
            <a href="https://afdian.net/a/sakura_society" class="
                block
                px-3
                py-2
                text-base
                font-medium
                text-gray-700
                rounded-md
                hover:text-gray-900 hover:bg-gray-50
              ">afdian</a>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import { mixin as clickaway } from 'vue-clickaway'

export default {
  mixins: [clickaway],
  data () {
    return {
      menuState: false,
      dropdownState: false,
    }
  },
  methods: {

    showCont () {
      this.show = !this.show;
    },
    closeDropdown () {
      this.dropdownState = false
    },
    closeMenu () {
      this.menuState = false
    },
  },
}
</script>

<style>
.left-21 {
  left: 200px;
}
</style>
