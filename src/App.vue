<template>
  <div id="app">
    <Nav/>
    <transition name="fade" mode="out-in">
        <router-view/>
    </transition>
  </div>
</template>

<script>
import Nav from './components/Nav'

  export default {
    components: {
      Nav
    },
    data() {
      return {
      };
    },
    methods: {
   
    },
  }
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Spartan:wght@500;700&display=swap');

body {
  margin: 0;
}

#app {
  //typo
  $spartan: 'Spartan', sans-serif;
  //colors
  $veryDarkBlue: #1B1D23;
  $darkGrey: #60636D;
  $mediumGrey: #7D828F;
  $lightGrey: #C8CCD8;
  $veryLightGrey: #EEEFF4;
  $red: #DF5656;
  $white: #FFF;


  h1, .h1-bis, h2, h3, p, a {
      font-family: $spartan;
  }
  h1, .h1-bis, h2, h3 {
      font-weight: bold;
  }

  h1, h2, h3 {
      color: $veryDarkBlue;
  }

  .h1-bis {
      font-size: 200px;
      line-height: 200px;
      color: $veryLightGrey;
  }

  h1 {
      font-size: 80px;
      line-height: 80px;
  }

  h2 {
      font-size: 56px;
      line-height: 56px;
  }

  h3 {
      font-size: 18px;
      line-height: 25px;
  }

  p {
      font-size: 15px;
      line-height: 25px;
      color: $darkGrey;
  }

  a {
      font-size: 15px;
      line-height: 25px;
      color: $mediumGrey;
      transition: .5s color ease;
      &:hover {
        color: $veryDarkBlue;
      }
  }

//transition router
.fade-enter-active, .fade-leave-active {
  transition: 0.3s opacity ease;
}

.fade-enter, .fade-leave-active {
  opacity: 0
}
  
}

</style>
