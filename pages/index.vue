<template>
  <section class="container">
    <div>
      <h1 class="title" @click="newsTime">
        PaperBoy Web
      </h1>
      <h2 class="subtitle" @click="newsTime">
        a GoonTuna production..
      </h2>
      <div class="links">
        <router-link to="/news">News</router-link>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  methods: {
    newsTime () {
      window.location('/news')
      // window.alert('click')
    }
  }
}
</script>

<style lang="stylus" scoped>
.container {
  // min-height: 90vh;
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

.links {
  padding-top: 15px;
}
</style>
