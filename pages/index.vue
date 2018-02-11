<template>
  <layout>
    <template slot='content'>
      <h1>Batman TV Shows</h1>
      <ul>
        <li v-for='{ show } in shows' :key='show.id'>
          <nuxt-link :to='`/post/${show.id}`'>{{show.name}}</nuxt-link>
        </li>
      </ul>
    </template>
  </layout>
</template>

<script>
import Layout from '~/components/Layout.vue'
import axios from 'axios'

export default {
  components: {
    Layout
  },
  async asyncData () {
    let { data } = await axios.get('http://api.tvmaze.com/search/shows?q=batman')
    return { shows: data }
  }
}
</script>

<style>

</style>
