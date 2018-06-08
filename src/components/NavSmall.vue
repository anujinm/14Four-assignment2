<template lang="pug">
  .nav
    button(@click="showMenu = !showMenu") 
      hamburger
    .show.row(v-if="showMenu")
      .col-3
        button.solutions(@click="showOptions = !showOptions") Solutions  ▾
        .options.sol(v-if="showOptions")
          a solution 1
          br
          a solution 2
          br
          a solution 3
      .col-1
        .vertical-line
      .col-3
        router-link.t5(to="/" v-bind:class="{ isInactive: !isRoot }") About us
        br
        router-link.t5(to="/other") Clients
        br
        router-link.t5(to="/other") News & Events
        br
        router-link.t5(to="/other") Contact us
      .col-1
        .vertical-line
      .col-3
        button.right.demo Demo
        button.right.language(@click="showOptionsLang = !showOptionsLang")
          i.fas.fa-globe &nbsp; EN ▾
        .options.lan(v-if="showOptionsLang")
          p English
          p Español
</template>

<script>
import debug from 'debug'
import hamburger from '@/components/Hamburger'
let log = debug('component:NavSmall')
export default {
  name: 'navSmall',
  props: [],
  data () {
    return {
      showMenu: false,
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
    'hamburger': hamburger
  }
}
</script>

<style scoped lang="scss">
@import "../styles/_variables";
@import "../styles/_mixins";
.nav {
  z-index: 1;
  position: absolute;
  left: 5%;
  top: 1%; 
  padding: 10px;
  font-size: 12px;
  button {background: transparent; border: none; outline: none; height: 30px;}
  .show {
    padding: 10px;
    background: linear-gradient($main-blue,$main-blue,$main-blue,$main-blue, transparent);
    filter: blur(0.3px);
    z-index: 1;
    width: 300px;
    transform: translateY(26%);
    padding-left:0px;
    margin-left: -50px;;
    height: 130px;
    transition: all 0.5s ease-in-out; 
    .col-3 {
      padding: 5px;
      a {
        color: white; 
        &:hover{
          color: $gray-text;
        }
      }
      button { 
        color: white;
        background: transparent;
        border: none;
        outline: none;
        &.demo{
          background: $light-blue;
          height:20px;
          border-radius: 30%;
        }
      }

      .options {
        &.lan {
          p {font-size: 10px; color: white; padding-left: 15px;}
        }
        &.sol {
          width: 80px;
          a {padding-left: 10px; }
        }
      }
    }
  }
  .col-1 {
    padding: 5px;
  }
  .vertical-line {
    height: 70px;
    top: 5px;
    border-right: 1px solid white;
    position: relative;
  }
}
  .router-link-active {
    color: $brandPrimary;
    &.isInactive {
      background: transparent;
      color: $brandPrimary;
    }
  }
</style>
