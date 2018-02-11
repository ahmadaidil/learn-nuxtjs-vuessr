<template>
  <div class='layout'>
    <Header />
    <slot name='content' />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
export default {
  components: {
    Header
  }
}
</script>