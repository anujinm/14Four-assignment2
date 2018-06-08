<template lang="pug">
  #app
    app-nav-full.full
    //- app-nav-small.small
    app-nav.normal
    app-home
    //- transition(name="vt-page")
    router-view
</template>

<script>
import Nav from '@/components/Nav'
import NavSmall from '@/components/NavSmall'
import NavFull from '@/components/NavFull'
import Home from '@/pages/Home'
import Other from '@/pages/Other'
import debug from 'debug'
let log = debug('App')
export default {
  name: 'app',
  mounted: function () {
    log('App Mounted')
    this.$store.dispatch('loading', false)
  },
  computed: {
  },
  methods: {
  },
  components: {
    'app-nav': Nav,
    'app-nav-small': NavSmall,
    'app-nav-full': NavFull,
    'app-home': Home,
    'app-other': Other
  }
}
</script>

<style lang="scss">
@import "./styles/main";
#app {
  border: 1px solid;
  font-family: Arial;
  .full { visibility: hidden; }
  @media #{$mobile} {
    .normal { visibility: hidden; }
    .full { visibility: visible; }
  }
}
</style>
