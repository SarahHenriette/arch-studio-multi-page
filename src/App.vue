<template>
  <div id="app">
    <div class="page-name">
        <div class="line"></div>
        <p>{{$route.name}}</p>
    </div>
    <Nav/>
    <transition name="fade" mode="out-in">
        <router-view/>
    </transition>
    <Footer/>
  </div>
</template>

<script>
import Nav from './components/Nav'
import Footer from './components/Footer'
// import { gsap } from "gsap";

  export default {
    components: {
      Nav,
      Footer
    },
    data() {
      return {
      };
    },
     mounted() {
        // gsap.to('.menu-burger', {rotation: 180, duration: 1})
   
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
  position: relative;

  h1, .h1-bis, h2, h3, p, a, input, textarea {
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
      @media screen and (max-width: 1110px) {
        font-size: 120px;
      }
  }

  h1 {
      font-size: 80px;
      line-height: 80px;
      @media screen and (max-width: 750px) {
        font-size: 48px;
        line-height: 48px;
      }
  }

  h2 {
      font-size: 56px;
      line-height: 56px;
      @media screen and (max-width: 750px) {
        font-size: 40px;
        line-height: 48px;
      }
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

  ul {
    padding-left: 0;
  }

  li {
    list-style-type: none;
  }
  a {
      font-size: 15px;
      line-height: 25px;
      color: $mediumGrey;
      transition: .5s color ease;
      text-decoration: none;
      font-weight: bold;
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


//buttons 
.btn-1 {
    height: 72px;
    background-color: $veryDarkBlue;
    color: $white;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: .5s color ease, .5s background-color ease;
    &:hover {
        background-color: $darkGrey;
        color: $white;
    }
    &:active {
        background-color: $lightGrey;
    }
}

.btn-2 {
    width: 80px;
    height: 80px;
    background-color: $veryDarkBlue;
    color: $white;
    &:hover {
        background-color: $darkGrey;
    }
    &:active {
        background-color: $lightGrey;
    }
}

.btn-3 {
    width: 80px;
    height: 80px;
    background-color: $white;
    color: $veryDarkBlue;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: $spartan;
    font-size: 15px;
}
.btn-3.active {
    background-color: $veryDarkBlue;
    color: $white;
}

.page-name {
  width: 450px;
  height: 25px;
  position: absolute;
  top: 125px;
  left: -147px;
  display: flex;
  align-items: center;
  transform: rotate(90deg);
  .line {
    width: 140px;
    height: 1px;
    background-color: $lightGrey;
    margin-right: 48px;
  }
  p {
    // transform: rotate(90deg);
    text-transform: uppercase;
    letter-spacing: 15px;
    font-size: 18px!important;
    margin: 0;

  }
}
  
}

@media screen and (max-width: 1110px){
  #app {
    .page-name {
          left: -176px;
    }
  }
}
@media screen and (max-width: 600px){
  #app {
    .page-name {
      display: none;
    }
  }
}

</style>
