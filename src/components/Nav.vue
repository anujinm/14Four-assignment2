<template lang="pug">
  .nav
    //- router-link.t4(to="/" v-bind:class="{ isInactive: !isRoot }") Landing
    button.t5.solutions(@click="showOptions = !showOptions") Solutions  ▾
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
  font-family: 'Roboto', sans-serif;
  z-index: 1;
  left: 10%;
  top: 2.0%;
  position: absolute;
  width: 100%;
  br {
    visibility: hidden;
  }
  
  a {
    color: white;
    display: inline-block;
    padding: 10px;
    font-size: 14px;
    &:hover {
      color: gray;
      cursor: pointer;
    }
  }
  button {
    cursor: pointer;
    outline: none;
    font-size: 14px;
    font-weight: 100 !important;
    &.solutions {
      background: transparent;
      border: none;
      color: white;
      font-weight: normal;
    }
    &.right {
      border: none;
      position: relative;
      right: -45%;
      margin-left: 10px;
      &.demo {
        font-size: 12px;
        background: $light-blue;
        border-radius: 2px;
        width: 75px;
        height: 30px;
        box-shadow: 0px 2px 8px rgb(9, 9, 77);
      }
      &.language {
        background: transparent;
        color: white;
      }
    }
  }

  .options {
    border-bottom: 1px solid white;
    color: black;
    background: transparent;
    line-height: 0;
    a {
      font-size: 12px;
      font-weight: 100;
    }
    p {
      color: white;
      position: relative;
      font-size: 10px;
      font-weight: 100;
    }
    
    &.sol {
      z-index: 1;
      bottom: 0;
      position: absolute;
      display: block;
      transform: translateY(100%);
      width: 80px;
      height: 45px;
      
    }
    &.lan {
      z-index: 1;
      bottom: 0;
      right: -42%;
      position: relative;
      transform: translateY(100%);
      width: 40px;
      height: 35px;
    }
  }

  .router-link-active {
    border: none;
    &.isInactive {
      background: transparent;
      color: $white; 
    }
    &.isInactive:before{
      content: "";
      height: 27px;
      display: block;
      margin: 0 auto;
      width: 90%;
      margin-top: -28px;
      border-top: 2px solid white;
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
  @media screen and (max-width: 1400px) {
    button {
      &.right{
        right: -33%;
      }
    }
    .options {
      &.lan {
        right: -30%;
      }
    }
  }
  @media #{$tablet} {
    button {
      &.right{
        right: -10%;
      }
    }
    .options {
      &.lan {
        right: -5%;
      }
    }
  }
  
}
</style>
