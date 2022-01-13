<template>
  <section class="container">
    <NuxtLink to="/embed">
      About (internal link that belongs to the Nuxt App)
    </NuxtLink>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  data() {
    return { isStripeLoaded: false }
  },
  head () {
    return {
      title: "Main page",
      script: [ { 
        id: 'usercentrics-cmp', 
        'data-settings-id': 'oMwnPm_KD', 
        src: 'https://app.usercentrics.eu/browser-ui/latest/loader.js', 
        async: true,
        callback: () => { this.isStripeLoaded = true } 
        } ]
    }
  },
  components: {
    AppLogo
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
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

