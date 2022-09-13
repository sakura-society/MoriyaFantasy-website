<template>
  <div>
    <Header />
    <Feature />
    <Cta />
    <Faq />
    <Rules />
    <Support />
    <Footer />
  </div>
</template>

<script>
export default {
  head () {
    const i18nHead = this.$nuxtI18nHead({ addSeoAttributes: true })
    return {
      htmlAttrs: {
        ...i18nHead.htmlAttrs,
      },
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            '守矢幻想是一款Minecraft服务器,旨在原版插件服务器中添加轻RPG元素',
        },
        ...i18nHead.meta,
      ],
      link: [
        {
          hid: 'apple-touch-icon',
          rel: 'apple-touch-icon',
          sizes: '180x180',
          href: '/apple-touch-icon.png',
        },
        ...i18nHead.link,
      ],
    }
  },
}
</script>