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
    <section id="leaders">
      <h2>The<br/> Leaders</h2>
      <div class="contain-profile-leaders">
        <Leader name="Jake Richards" job="Chief Architect"><template v-slot:img><img src="./../../public/about/desktop/avatar-jake.jpg" alt="portrait de bel homme avec des lunettes de soleil"></template></Leader>
        <Leader name="Thompson Smith" job="Head of Finance"><template v-slot:img><img src="./../../public/about/desktop/avatar-thompson.jpg" alt="portrait de bel homme noir"></template></Leader>
        <Leader name="Jackson Rourke" job="Lead Designer"><template v-slot:img><img src="./../../public/about/desktop/avatar-jackson.jpg" alt="portrait de bel homme brun et ténébreux"></template></Leader>
        <Leader name="Maria Simpson" job="Senior Architect"><template v-slot:img><img src="./../../public/about/desktop/avatar-maria.jpg" alt="portrait de belle femme brune et élégante"></template></Leader>
      
      </div>
    </section>

  </div>
</template>

<script>
import Header from './../components/HeaderAboutContact'
import Leader from './../components/About/Leader'
export default {
  components: {
    Header,
    Leader
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

    #leaders {
      width: 1110px;
      display: flex;
      justify-content: space-between;
      margin: auto;
      margin-top: 200px;
      
      h2 {
        margin: 0;
      }
      .contain-profile-leaders {
        width: 730px;
        height: 860px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
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
      #leaders {
        flex-direction: column;
        width: 572px;
        .contain-profile-leaders { 
          width: 572px;
          align-items: flex-end;
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

      #our-heritage {
        width: 311px;
        height: 508px;
        .contain-text-our-heritage {
          width: 311px;
          height: 425px;
        }

      }

      #leaders {
        flex-direction: column;
        width: 311px;
        height: 1896px;
        margin-top: 72px;
        .contain-profile-leaders { 
          width: 311px;
          height: 1736px;
          flex-direction: column;
          flex-wrap: nowrap;
        }
      }
    }
  }
</style>