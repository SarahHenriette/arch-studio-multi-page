<template>
  <div class="about">
    <Header title="Your team of professionals" 
    section="About" 
    text="Our small team of world-class professionals will work with you every step of the way. Strong relationships are at the core of everything we do. This extends to the relationship our projects have with their surroundings.">
       <template v-slot:image-header><div class="contain-image-header"></div></template>
    </Header>

  </div>
</template>

<script>
import Header from './../components/HeaderAboutContact'
export default {
  components: {
    Header
  }
}
</script>

<style lang="scss" scoped>
  .about {
    header {
      .contain-image-header {
        background-image: url('../../public/about/desktop/image-hero.jpg');
      }
    }
  }

  @media screen and (max-width: 750px) {
    .about {
      header {
        .contain-image-header {
          background-image: url('../../public/about/mobile/image-hero.jpg');
        }
      }
    }
  }
</style>