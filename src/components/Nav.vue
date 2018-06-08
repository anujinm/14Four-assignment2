<template lang="pug">
  .nav
    //- router-link.t4(to="/" v-bind:class="{ isInactive: !isRoot }") Landing
    button.solutions(@click="showOptions = !showOptions") Solutions  ▾
    .options.sol(v-if="showOptions")
      a solution 1
      a solution 2
    router-link.t5(to="/" v-bind:class="{ isInactive: !isRoot }") About us
    router-link.t5(to="/other") Clients
    router-link.t5(to="/other") News & Events
    router-link.t5(to="/other") Contact us
    br.br
    button.right.demo Demo
    button.right.language(@click="showOptionsLang = !showOptionsLang")
      i.fas.fa-globe &nbsp; EN ▾
    .options.lan(v-if="showOptionsLang")
      p English
      p Español
</template>

<script>
import debug from 'debug'
let log = debug('component:Nav')
export default {
  name: 'nav',
  props: [],
  data () {
    return {
      showOptions: false,
      showOptionsLang: false
    }
  },
  beforeCreate: function () {
  },
  mounted: function () {
    log('Mounted')
  },
  computed: {
    isRoot () {
      return this.$store.state.route.path === '/other'
    }
  },
  methods: {
  },
  components: {
  }
}
</script>

<style scoped lang="scss">
@import "../styles/_variables";
@import "../styles/_mixins";
.nav {
  z-index: 1;
  left: 10%;
  top: 3%;
  position: absolute;
  br {
    visibility: hidden;
  }
  .options {
    border-bottom: 1px solid white;
    color: black;
    background: transparent;
    a {
      font-size: 15px;
      font-weight: 100;
    }
    p {
      color: white;
      font-size: 10px;
      font-weight: 100;
    }
    
    &.sol {
      z-index: 1;
      bottom: 0;
      position: absolute;
      display: block;
      transform: translateY(100%);
      width: 90px;
      height: 80px;
    }
    &.lan {
      z-index: 1;
      bottom: 0;
      right: -45%;
      position: absolute;
      transform: translateY(100%);
      width: 70px;
      height: 50px;
    }
  }
  a {
    color: white;
    display: inline-block;
    padding: 10px;
    font-size: 17px;
    &:hover {
      color: gray;
      cursor: pointer;
    }
  }
  button {
    outline: none;
    font-size: 15px;
    &.solutions {
      background: transparent;
      border: none;
      color: white;
    }
    &.right {
      border: none;
      position: relative;
      right: -45%;
      margin-left: 10px;
      &.demo {
        background: $light-blue;
        border-radius: 20px;
        width: 80px;
        height: 30px;
      }
      &.language {
        background: transparent;
        color: white;
      }
    }
  }

  .router-link-active {
      border: none;
    &.isInactive {
      background: transparent;
      color: $brandPrimary;
      border-top: 1px solid white;
    }
  }

  @media #{$mobile} {
    top: 0;
    left:0;
    br { visibility: visible; }
    a { font-size: 10px; }
    .options {
      a {font-size: 10px; padding: 0;}
      &.sol {
        width: 45px;
        height: 60px;
        top: -40px;
        left: 10px;
      }
      &.lan { right: 0%; width: 35px; }
    }
    button{
      font-size: 10px;
      &.right {
        position: absolute;
        top: 70%;
        right: 20%;
        &.demo { width: 40px; height: 20px; }
        &.language { right: 0%;}
      }
    }
  }
}
</style>
