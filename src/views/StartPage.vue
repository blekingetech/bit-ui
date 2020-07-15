<template>
  <div>
    {{ webPage.content[0].body }}
  </div>
</template>

<script>
// @ is an alias to /src
import getWebPage from '../apollo/queries/webpage.graphql'

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
}
</script>
