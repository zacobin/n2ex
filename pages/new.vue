<template>
  <topic-list-chalk :topic-list="newList" />
</template>

<script>
import TopicListChalk from '~/components/TopicListChalk'

export default {
  head () {
    return {
      titleTemplate: '%s - 最新'
    }
  },
  components: {
    TopicListChalk
  },
  async asyncData ({ app }) {
    const { data } = await app.$axios.get('topics/latest.json')

    return {
      newList: data
    }
  }
}
</script>
