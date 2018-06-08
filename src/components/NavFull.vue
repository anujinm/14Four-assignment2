<template lang="pug">
  .nav
    button(@click="showMenu = !showMenu") 
      hamburger
    transition(name="slide" type="animation")
      .show(v-if="showMenu")
        .lines
          button.solutions(@click="showOptions = !showOptions") Solutions  ▾
          .options.sol(v-if="showOptions")
            a solution 1
            br
            a solution 2
            br
            a solution 3
          hr
          // .shiftDown(:class="{shift: showOptions}")
          router-link.t5(to="/" v-bind:class="{ isInactive: !isRoot }") About us
          hr
          router-link.t5(to="/other") Clients
          hr
          router-link.t5(to="/other") News & Events
          hr
          router-link.t5(to="/other") Contact us
          hr
          button.demo Demo
          button.language(@click="showOptionsLang = !showOptionsLang")
            i.fas.fa-globe &nbsp; EN ▾
          .options.lan(v-if="showOptionsLang")
            p English
            p Español

</template>

<script>
import debug from 'debug'
import hamburger from '@/components/Hamburger'
let log = debug('component:NavFull')
export default {
  name: 'navFull',
  props: [],
  data () {
    return {
      showMenu: true,
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
  .hamburger {
    z-index: 3;
  }
  button {background: transparent; border: none; outline: none; height: 30px;}
  .show{
    width: 414px;
    height: 1550px;
    margin-left:-20px;
    margin-top: -40px;
    background: linear-gradient($main-purple, $main-blue); 
    z-index: 2;
    transition: all 0.5s ease-in-out; 
  }
  hr {
    margin: 15px;
  }
  .lines {
    a { 
      color: white; 
      // border-bottom: 2px solid white;
      &:hover {color: gray;}
    }
    button { 
      color: white;
      margin:10px;
      &.demo {
        background: $light-blue;
        height:40px;
        width: 90px;
        border-radius: 20px;;
        &:hover { transform: scale(1.1,1.1); }
      } 
    }
    .options {
      &.sol {
        a {font-size: 20px; border: none; &:hover {color: gray;}}
      }
      &.lan {p {font-size: 15px; color: white; padding-left: 110px;}}
    }
    padding-top:100px;
    text-align: center;
    .shift {
      // margin-top: 20%;
      // transition: all 0.1s ease-in-out; 
    }
  }
  .slide-enter{
    opacity: 0;
  }
  .slide-enter-active{
    animation: slide-in 1s ease-out forwards;
    transition: opacity .5s;
  }
  .slide-leave {
  }
  .slide-leave-active {
    animation: slide-out 1s ease-out forwards;
    transition: opacity 3s;
    opacity: 0;
  }
  @keyframes slide-in {
    from {
      transform: translateY(-100px);
    } to {
      transform: translateY(0);
    }
  }
  @keyframes slide-out {
    from {
      transform: translateY(0);
    } to {
      transform: translateY(-100px);
    }
  }
}
</style>
