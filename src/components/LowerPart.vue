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
      .row.justify-content-center
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
.lower {
  position: relative;
  overflow: hidden;
  height: 18em;
  .box {
    &:hover {
    transform: scale(1.1,1.1);
    transition: all .5s ease-in-out;
    }
    img { max-width: 60px; }
    h5 { font-size: 20px; }
    p { font-size: 15px; color: gray; }
    button {
      font-size: 10px;
      width: 50%;
      height: 10%;;
      border: 1px solid $main-blue;
    }
    transition: all .5s ease-in-out;
    padding: 20px;
    font-family: Arial;
    width: 200px;
    height: 250px;
    box-shadow: 5px 5px 25px 5px gray;
    }
  .row {
    padding: 40px;
  }
  .circleGray {
    border-radius: 50%;
    width: 120%;
    height: 150%;
    background: #EBEBEB;
    position: absolute;
    bottom: -105%;
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
