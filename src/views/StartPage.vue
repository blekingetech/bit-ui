<template>
  <div>
    <div v-if="!$apollo.loading" v-html="markdown(webPage.content[0].body)"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import getWebPage from '../apollo/queries/webpage.graphql'
import marked from 'marked'

export default {
  name: 'StartPage',
  apollo: {
    webPage: {
      variables: {
        uri: '/',
      },
      query: getWebPage
    }
  },
  methods: {
    markdown(source) {
      marked.setOptions({
        render: new marked.Renderer()
      })
      return marked(source)
    }
  }
}
</script>
