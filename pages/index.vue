<template>
  <ul>
    {{ about }}
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      about: null
    };
  },
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://leone-9.microcms.io/api/v1/about',
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { 'X-API-KEY': '5d033a57-ceb0-42fc-8949-ecaf6da6cbb0' }
      }
    )
    return {
      about: data.about
    }
  }
}
</script>