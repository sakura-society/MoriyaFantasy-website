<template>
  <div class="article-body">
    <nuxt-content class="w-full mt-4 nuxt-content dark:nuxt-content-dark max-w-none" :document="article" />
  </div>
</template>

<script>
export default {
  props: {
    article: {
      default: () => { },
      required: true,
      type: Object,
    },
  },
}
</script>
<style>
.nuxt-content {
  display: grid;
  grid-template-columns: 100%;
  grid-auto-rows: auto;
  grid-gap: 32px 0;
  gap: 32px 0;
  margin-top: 40px;
}

.nuxt-content blockquote,
.nuxt-content dd,
.nuxt-content dl,
.nuxt-content figure,
.nuxt-content h1,
.nuxt-content h2,
.nuxt-content h3,
.nuxt-content h4,
.nuxt-content h5,
.nuxt-content h6,
.nuxt-content hr,
.nuxt-content p,
.nuxt-content pre {
  margin: 0;
}

.nuxt-content h1,
.nuxt-content h2,
.nuxt-content h3,
.nuxt-content h4,
.nuxt-content h5 {
  margin: 1.25em;
}

@media (min-width: 768px) {
  .nuxt-content h1 {
    font-size: 3rem;
    line-height: 1;
    color: #b91c1c;
    letter-spacing: -.025em;
    font-weight: 700;
    margin-bottom: 1rem;
  }
}

.nuxt-content h1 {
  font-size: 1.875rem;
  line-height: 2.25rem;
  color: #b91c1c;
  letter-spacing: -.025em;
  font-weight: 700;
  margin-bottom: 1rem;
}

.nuxt-content h2,
.nuxt-content h3,
.nuxt-content h4 {
  scroll-margin-top: 8rem;
}

.nuxt-content h2 {
  color: #b91c1c;
  font-weight: 700;
  font-size: 1.5em;
  margin-top: 2em;
  margin-bottom: 1em;
  line-height: 1.3333333;
}

.nuxt-content p {
  margin-top: 1.25em;
  margin-bottom: 1.25em;
}

.article-toc,
.nuxt-content p,
.nuxt-content li,
.nuxt-content ul,
.nuxt-content blockquote {
  margin-left: 3em;
  margin-right: 3em;
  --tw-text-opacity: 1;
  color: rgba(107, 114, 128, var(--tw-text-opacity));
}

.nuxt-content menu,
.nuxt-content ol,
.nuxt-content ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.nuxt-content ul {
  list-style-type: disc;
  color: #6b7280;
  margin-top: 1.25em;
  margin-bottom: 1.25em;
  padding-left: 1.625em;
}

.nuxt-content :where(ul>li) {
  padding-left: .375em;
}

.nuxt-content li {
  margin-top: .5em;
  margin-bottom: .5em;
}

.nuxt-content h2+* {
  margin-top: 0;
}

.nuxt-content blockquote {
  font-weight: 500;
  font-style: italic;
  color: #fecaca;
  border-left-width: .25rem;
  border-left-color: #fee2e2;
  quotes: "\201C" "\201D" "\2018" "\2019";
  margin-top: 1.6em;
  margin-bottom: 1.6em;
  padding-left: 1em;
}

.nuxt-content a {
  transition-property: all;
  transition-timing-function: cubic-bezier(.4, 0, .2, 1);
  transition-duration: .15s;
}

.nuxt-content :where(.nuxt-content>ul>li>:last-child) {
  margin-bottom: 1.25em;
}

.nuxt-content :where(.nuxt-content>ul>li>:first-child) {
  margin-top: 1.25em;
}

.nuxt-content :where(a) {
  color: #ef4444;
  text-decoration: underline;
  font-weight: 500;
}
</style>