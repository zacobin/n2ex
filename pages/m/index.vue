<template>
  <topic-list :topic-list="hotList" />
</template>

<script>
import TopicList from '~/components/TopicList'

export default {
  head () {
    return {
      titleTemplate: '%s - 最热'
    }
  },
  components: {
    TopicList
  },
  async asyncData ({ app }) {
    const { data } = await app.$axios.get('topics/hot.json')

    return {
      hotList: data
    }
  },
  layout: 'mobile'
}
</script>
