<template>
    <div >
      <ul id="nav" > 
        <li v-if="$route.name !== 'Home'"><router-link to="/" class="logo-link"><Logo/></router-link> </li>
        <li v-else><Logo/></li>
        <li><router-link to="/portfolio">Portfolio</router-link></li>
        <li><router-link to="/about">About Us</router-link></li>
        <li><router-link to="/contact">Contact</router-link></li>
      </ul>
      <div id="nav-mobile" >
        <router-link to="/"><Logo/></router-link> 
          <svg xmlns="http://www.w3.org/2000/svg"  class="menu-close" v-if="menuMobile" @click="changeMenuMobile" width="20" height="21"><path fill="#1B1D23" fill-rule="evenodd" d="M17.425.954l2.12 2.121-7.424 7.425 7.425 7.425-2.121 2.12L10 12.622l-7.425 7.425-2.12-2.121L7.878 10.5.454 3.075 2.575.955 10 8.378 17.425.954z"/></svg>
          <svg xmlns="http://www.w3.org/2000/svg"  class="menu-burger" v-else @click="changeMenuMobile" width="24" height="17"><g fill="#1B1D23" fill-rule="evenodd"><path d="M0 0h24v3H0zM0 7h24v3H0zM0 14h24v3H0z"/></g></svg>
        <transition name="slide" mode="out-in">
          <div v-if="menuMobile" class="nav-mobile-menu">
            <ul>
              <li><router-link to="/portfolio">Portfolio</router-link></li>
              <li><router-link to="/about">About Us</router-link></li>
              <li><router-link to="/contact">Contact</router-link></li>
            </ul>
          </div>
        </transition>
      </div>
    </div>

</template>

<script>
import { gsap } from "gsap";
import Logo from './Logo'

export default {
  components: {
    Logo,
  },

  data () {
    return {
      menuMobile: false,
    }
  },
  mounted() {
    // gsap.to('.menu-burger', {x:500, duration: 3})
  },
  methods: {
    changeMenuMobile() {
      this.menuMobile = !this.menuMobile
      gsap.to('.menu-close', {x:-50, duration: 3})
      gsap.to('.menu-burger', {x:-50, duration: 3})

    }
  },

}
</script>

<style lang="scss" scoped>
$veryLightGrey: #EEEFF4;
$veryDarkBlue: #1B1D23;

  #nav, #nav-mobile {
    display: flex;
    justify-content: space-between;
    align-items: center;
    li {
      list-style: none;
    }
    a {
      text-decoration: none;
      padding: 15px;
      font-weight: bold;
    }
  }
  #nav {
    width: 507px;
    height: 40px;
    margin: 56px 769px 56px 164px;
    padding-left: 0;
    .logo-link {
      line-height: 0;
      padding: 0;
    }
  }
  #nav-mobile {
    display: none;
    width: 311px;
    height: 32px;
    margin: 32px auto 32px auto;
    .nav-mobile-menu {
      width: 343px;
      height: 235px;
      position: absolute;
      background-color: $veryLightGrey;
      right: 0;
      top: 96px;
      ul {
        width: 247px;
        height: 139px;
        margin: 48px auto;
        padding-left: 0;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        animation: test .5s .6s;
        opacity: 1;
        li a {
          color: $veryDarkBlue;
          animation: test .5s .6s;
          opacity: 1;
        }

        @keyframes test {
          0%{opacity: 0;}
          100%{opacity: 1;}
        }
        
      }
    }
    .slide-enter-active, .slide-leave-active {
      transition: 0.3s height ease;
    }

    .slide-enter, .slide-leave-active {
      height: 10px;
    }
  }

  @media screen and (max-width: 1200px){
    #nav {
      width: 491px;
      margin: 56px 180px 56px 97px;
    }
  }
  @media screen and (max-width: 450px){
    #nav {
      display: none;
    }

    #nav-mobile {
      display: flex;
    }
  }
</style>