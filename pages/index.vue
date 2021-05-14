<template>
  <div>
    <nuxt-link to="/articles/1">test page</nuxt-link>
  </div>
</template>

<script>
import meta from '@/assets/data/meta-tag.json'

export default {
  data() {
    return {
      metaData: meta.metaDetail,
    }
  },
  head() {
    return {
      title: this.metaData.title,
      meta: [
        {
          hid: 'og:title',
          name: 'og:title',
          content: this.metaData.title,
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: this.$route.fullPath,
        },
        {
          hid: 'og:type',
          name: 'og:type',
          content: 'article',
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: this.metaData.description,
        },
        {
          hid: 'og:image',
          name: 'og:image',
          content: this.metaData.image,
        },
      ],
    }
  },
}
</script>
