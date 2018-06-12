<template lang="pug">
  .lower
    .container
      .row.justify-content-center
        .col-sm-3
          lower-box-1.box
        .col-sm-3
          lower-box-2.box
        .col-sm-3
          lower-box-3.box
      .row.justify-content-center.lowertext
        .col-sm-2
          lower-text-1(:number="number1" :word="word1")
        .col-sm-2
          lower-text-1(:number="number2" :word="word2")
        .col-sm-2
          lower-text-1(:number="number3" :word="word3")
    .circleGray
</template>

<script>
import debug from 'debug'
import lowerBox1 from '@/components/LowerBox1'
import lowerBox2 from '@/components/LowerBox2'
import lowerBox3 from '@/components/LowerBox3'
import lowerText1 from '@/components/LowerText1'
let log = debug('component:LowerPart')
export default {
  name: 'lower',
  props: [],
  data () {
    return {
      number1: '780+',
      number2: '200+',
      number3: '25+',
      word1: 'customers',
      word2: 'clients',
      word3: 'countries'
    }
  },
  beforeCreate: function () {
  },
  mounted: function () {
    log('Mounted')
  },
  computed: {
  },
  methods: {
  },
  components: {
    'lower-box-1': lowerBox1,
    'lower-box-2': lowerBox2,
    'lower-box-3': lowerBox3,
    'lower-text-1': lowerText1
  }
}
</script>

<style lang="scss">
@import "../styles/_variables";
.container {
}
.lower {
  position: relative;
  overflow: hidden;
  height: 420px;
  .box {
    &:hover {
    transform: scale(1.1,1.1);
    transition: all .5s ease-in-out;
    }
    img { max-width: 60px; }
    h5 { font-size: 18px; padding-top: 10px; margin-bottom : 5px;}
    p { font-size: 13px; color: #a8a8a8; margin:0; padding-bottom: 5px;}
    button {
      font-size: 10px;
      width: 40%;
      height: 12%;
      border: 1px solid $main-blue;
      padding: 5px;
      cursor: pointer;
      &:hover { transform: scale(1.2,1.2); }
    }
    transition: all .5s ease-in-out;
    padding: 15px;
    font-family: Arial;
    width: 210px;
    height: 220px;
    padding: 20px;
    box-shadow: 1px 2px 20px 2px #c7c7c7;
    border-radius: 5px;
    }
  .row {
    padding: 10px;
  }
  .lowertext {
    padding-top: 50px;
  }

  .circleGray {
    border-radius: 50%;
    width: 120%;
    height: 150%;
    background: #EBEBEB;
    position: absolute;
    bottom: -98%;
    right: -50%; 
    z-index: -1;
    overflow: hidden;
  }

  @media #{$mobile} {
    height: auto;
    .col-sm-3 {
      left: 13%;
      padding-bottom: 20px;
    }
  }
}
</style>
