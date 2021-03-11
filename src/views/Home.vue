<template>
  <div class="home">
<header>
      <div class="slides">
        <Slide v-for="slide in slider" :key="slide.title" :class="slide.className"  >
            <template v-slot:title>{{ slide.title }}</template>
            <template v-slot:text>{{ slide.text }}</template>
        </Slide>
    </div>
     <div class="bar-slide">
          <div class="btn-3 active">01</div>
          <div class="btn-3">02</div>
          <div class="btn-3">03</div>
          <div class="btn-3">04</div>
        </div>
</header>

  </div>
</template>

<script>
// @ is an alias to /src
import { gsap } from "gsap";
import Slide from './../components/Home/Slide'
export default {
  name: 'Home',
  components: {
    Slide
  },
  data () {
    return {
      slider: [
         { id:"01", title:"Project Paramour", text: "Project made for an art museum near Southwest London. Project Paramour is a statement of bold, modern architecture.", className:"slide-project-paramour active"},
         { id:"02", title:"Seraph Station", text: "The Seraph Station project challenged us to design a unique station that would transport people through time. The result is a fresh and futuristic model inspired by space stations.", className:"slide-seraph-station"},
         { id:"03", title:"Federal II Tower", text: "A sequel theme project for a tower originally built in the 1800s. We achieved this with a striking look of brutal minimalism with modern touches.", className:"slide-federal-tower"},
         { id:"04", title:"Trinity Bank Tower", text: "Trinity Bank challenged us to make a concept for a 84 story building located in the middle of a city with a high earthquake frequency. For this project we used curves to blend design and stability to meet our objectives.", className:"slide-trinity-bank-tower"}
      ],
      i: 0,
      interval: null,
    }
  },
  mounted () {
    console.log(this.$route)
    gsap.fromTo('.slides', {y: -100}, {y: 0, duration: 0.5, ease: "linear"})
        this.interval = setInterval(() => {
          let slides = document.querySelectorAll('.slide')
          slides.forEach(slide => {
            console.log(slide)
            slide.style.transition= ""
            if (window.matchMedia("(max-width: 1110px)").matches) {
              slide.style.transform=" translateX(573px)"
            }else if (window.matchMedia("(max-width: 1110px)").matches) {
              slide.style.transform=" translateX(375px)"
            }else {
              slide.style.transform=" translateX(1110px)" 
            }
             
          });
          this.showSlide(this.i + 1)
        }, 2000);
  },
  methods: {
        showSlide (value) {
          let slides = document.querySelectorAll('.slide')
          let btn = document.querySelectorAll('.btn-3')

          slides[this.i].classList.remove('active')
          btn[this.i].classList.remove('active')
              if (window.matchMedia("(max-width: 1110px)").matches) {
                 slides[this.i].style.transform=" translateX(-573px)"
              }else if (window.matchMedia("(max-width: 1110px)").matches) {
                 slides[this.i].style.transform=" translateX(-375px)"
              }else {
                slides[this.i].style.transform=" translateX(-1110px)" 
              }
              slides[this.i].style.transition=" transform .5s linear"
          this.i = value    
          if(this.i> slides.length-1){ 
            this.i= 0
            }
          if(this.i == -1) { this.i= slides.length-1 }

          slides[this.i].classList.add('active')

          btn[this.i].classList.add('active')
        

          // 
          gsap.fromTo('.btn-3.active', {y: -50}, {y: 0, duration: 1})

        }
  },
  beforeDestroy () {
    clearInterval(this.interval)
  }
}
</script>

<style lang="scss" scoped>
  .home {
    header {
      width: 1110px;
      position: relative;
      margin: auto;
          .slides {
          width: 1110px;
          height: 720px;
          margin: auto;
          position: relative;
          overflow: hidden;
          .active {
            display: flex;
            transform: translateX(0)!important;
            transition: transform .5s linear;
            z-index: 900;
          }
          .slide-project-paramour {
            background-image: url('../../public/home/desktop/image-hero-paramour.jpg');
          }
          .slide-seraph-station {
            background-image: url('../../public/home/desktop/image-hero-seraph.jpg');
          }
          .slide-federal-tower {
            background-image: url('../../public/home/desktop/image-hero-federal.jpg');
          }
          .slide-trinity-bank-tower {
            background-image: url('../../public/home/desktop/image-hero-trinity.jpg');
          }
        }
          .bar-slide {
            width: 320px;
            height: 80px;
            display: flex;
            position: absolute;
            bottom: 0;
            left: -80px;
            z-index: 901;
            .btn-3 {
              cursor: pointer;
            }
          }
    }
  }


  @media screen and (max-width: 1110px) {
    .home {
      header {
        width: 573px;
        .slides {
        width: 573px;
        height: 720px;
        .slide-project-paramour {
          background-image: url('../../public/home/tablet/image-hero-paramour.jpg');
        }
        .slide-seraph-station {
          background-image: url('../../public/home/tablet/image-hero-seraph.jpg');
        }
        .slide-federal-tower {
          background-image: url('../../public/home/tablet/image-hero-federal.jpg');
        }
        .slide-trinity-bank-tower {
          background-image: url('../../public/home/tablet/image-hero-trinity.jpg');
        }
      }
        .bar-slide {
          display: none;
        }
      }
    }
  }

  @media screen and (max-width: 750px) {
    .home {
      header {
        .slides {
        width: 100%;
        height: 560px;
        .slide-project-paramour {
          background-image: url('../../public/home/mobile/image-hero-paramour.jpg');
        }
        .slide-seraph-station {
          background-image: url('../../public/home/mobile/image-hero-seraph.jpg');
        }
        .slide-federal-tower {
          background-image: url('../../public/home/mobile/image-hero-federal.jpg');
        }
        .slide-trinity-bank-tower {
          background-image: url('../../public/home/mobile/image-hero-trinity.jpg');
        }
      }
      }
    }
  }
</style>
