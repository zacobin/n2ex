<template>
  <topic-list-chalk :topic-list="techList" />
</template>

<script>
import { fetchTopicList } from '~/utils'
import TopicListChalk from '~/components/TopicListChalk'

export default {
  head () {
    return {
      titleTemplate: '%s - 技术'
    }
  },
  components: {
    TopicListChalk
  },
  async asyncData ({ app }) {
    const nodes = ['programmer', 'fe', 'js', 'nodejs', 'vue']
    const techList = await fetchTopicList(app.$axios, nodes)

    return {
      techList
    }
  }
}
</script>
