<template>
  <layout>
    <template slot='content'>
      <h1>{{show.name}}</h1>
      <p>{{show.summary.replace(/[\/]?p>/g, '')}}</p>
    </template>
  </layout>
</template>

<script>
import axios from 'axios'
import Layout from '~/components/Layout'
export default {
  components: {
    Layout
  },
  async asyncData ({ params }) {
    let { data } = await axios.get(`http://api.tvmaze.com/shows/${params.id}`)
    return { show: data }
  }
}
</script>