
  <template>
      <div>
        <div v-if="ucLoad" class="uc-embed" uc-data="all" uc-show-toggle="true" uc-styling="true" uc-embedding-type="category"></div>
        <NuxtLink to="/">Home page</NuxtLink>
        <div>{{this.ucLoad}}</div>
      </div>
    </template>
<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  data() {
    return { ucLoad: false}
  },
  head () {
    return {
      title: "Main page",
      script: [ {
          hid: 'usercentrics-cmp',
          id: 'usercentrics-cmp', 
          'data-settings-id': 'oMwnPm_KD', 
          src: 'https://app.usercentrics.eu/browser-ui/latest/loader.js', 
          defer: true,
          callback: () => { this.ucLoad = true}
        },
        {
          skip: !this.ucLoad,
        }]
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

