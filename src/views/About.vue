<template>
  <div class="about">
    <Header title="Your team of professionals" 
    section="About" 
    text="Our small team of world-class professionals will work with you every step of the way. Strong relationships are at the core of everything we do. This extends to the relationship our projects have with their surroundings.">
       <template v-slot:image-header><div class="contain-image-header"></div></template>
    </Header>
    <div id="our-heritage">
      <div class="contain-text-our-heritage">
        <h2>Our Heritage</h2>
        <p>Founded in 2007, we started as a trio of architects. Our complimentary skills and relentless attention to detail turned Arch into one of the most sought after boutique firms in the country.<br/><br/>
          Speciliazing in Urban Design allowed us to focus on creating exceptional structures that live in harmony with their surroundings. We consider every detail from every surrounding element to inform our designs<br/><br/>
          Our small team of world-class professionals provides input on every project.</p>
      </div>
      <div class="contain-image-our-heritage"></div>
    </div>

  </div>
</template>

<script>
import Header from './../components/HeaderAboutContact'
export default {
  components: {
    Header
  }, 

  mounted () {
    const scene3 = this.$scrollmagic.scene({
      triggerElement: '#our-heritage',
      triggerHook: 0.9,
      duration: 300
    }).setTween('.contain-image-our-heritage', {  
      css: { 
          transform: 'translateX("0")',
          transition: 'transform .2s linear',
      },
    })

    this.$scrollmagic.addScene(scene3)
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

    #our-heritage {
      width: 1110px;
      height: 568px;
      margin: 200px auto 0 auto;
      display: flex;
      justify-content: space-between;
      .contain-text-our-heritage {
        width: 446px;
        height: 568px;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        h2, p {
          margin: 0;
        }
        h2 {
          width: 300px;
          margin-bottom: 32px;
        }
      }
      .contain-image-our-heritage {
        width: 540px;
        height: 568px;
        background-image: url('../../public/about/desktop/image-heritage.jpg');
        transform: translateX(100px)
      }
    }
  }

  @media screen and (max-width: 1110px) {
    .about {
      #our-heritage {
        width: 574px;
        height: 518px;
        .contain-text-our-heritage {
          width: 573px;
          height: 443px;
        }
        .contain-image-our-heritage {
          display: none;
        }
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