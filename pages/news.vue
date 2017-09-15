<template lang="pug">
  section.container
    h2.title News
    router-link(to="/") Home
    ul
      li(v-for="item in items" :key="`item-${item.index}`")
        b
          a(:href="item.URL" title="item.SourceName") {{item.Title}}
          span(v-if="item.SourceName === 'HackerNews'" class="hackernews") Y
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  async asyncData ({ app }) {
    const items = await app.$axios.$get('/items')
    return { items }
  },
  data () {
    return {
      items: []
    }
  },
  async created () {
  }
}
</script>

<style lang="stylus" scoped>
ul
  padding 0
  margin 0
li
  padding 0.1em 0
  list-style none
.hackernews
  background-color #ff6600
  width 1em
  height 1em
  text-align center
  color white
  font-weight 700
  display inline-block
  font-size 0.7em
  line-height 1
  margin 0 0.5em

.container {
  // min-height: 100vh;
  // display: flex;
  // justify-content: center;
  // align-items: center;
  // text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

</style>
