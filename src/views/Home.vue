<template>
  <div class="home">
    <div class="slides">
        <Slide v-for="slide in slides" :key="slide.title" :class="slide.className"  >
            <template v-slot:title>{{ slide.title }}</template>
            <template v-slot:text>{{ slide.text }}</template>
        </Slide>
        <div class="bar-slide">
          <div class="btn-3 active">01</div>
          <div class="btn-3">02</div>
          <div class="btn-3">03</div>
          <div class="btn-3">04</div>
        </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Slide from './../components/Home/Slide'
export default {
  name: 'Home',
  components: {
    Slide
  },
  data () {
    return {
      slides: [
         { id:"01", title:"Project Paramour", text: "Project made for an art museum near Southwest London. Project Paramour is a statement of bold, modern architecture.", className:"slide-project-paramour active"},
         { id:"02", title:"Seraph Station", text: "The Seraph Station project challenged us to design a unique station that would transport people through time. The result is a fresh and futuristic model inspired by space stations.", className:"slide-seraph-station"},
         { id:"03", title:"Federal II Tower", text: "A sequel theme project for a tower originally built in the 1800s. We achieved this with a striking look of brutal minimalism with modern touches.", className:"slide-federal-tower"},
         { id:"04", title:"Trinity Bank Tower", text: "Trinity Bank challenged us to make a concept for a 84 story building located in the middle of a city with a high earthquake frequency. For this project we used curves to blend design and stability to meet our objectives.", className:"slide-trinity-bank-tower"}
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
  .home {
    .slides {
      width: 1110px;
      height: 720px;
      margin: auto;
      position: relative;
      .active {
        display: flex;
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
      .bar-slide {
        width: 320px;
        height: 80px;
        display: flex;
        position: absolute;
        bottom: 0;
        left: -80px;
      }
    }
  }

  @media screen and (max-width: 1110px) {
    .home {
      .slides {
        width: 573px;
        height: 720px;
        .bar-slide {
          display: none;
        }
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
    }
  }

  @media screen and (max-width: 750px) {
    .home {
      .slides {
        width: 100%;
        height: 560px;
        .bar-slide {
          display: none;
        }
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
</style>
