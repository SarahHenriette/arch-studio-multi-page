<template>
  <div class="home">
    <Header/>
    <section id="welcome">
      <h1 class="h1-bis">Welcome</h1>
      <article class="contain-text-welcome">
        <h2>Welcome to Arch Studio</h2>
        <p>We have a unique network and skillset to help bring your projects to life. Our small team of highly skilled individuals combined with our large network put us in a strong position to deliver exceptional results.<br/><br/>
          Over the past 10 years, we have worked on all kinds of projects. From stations to high-rise buildings, we create spaces that inspire and delight.<br/><br/>
          We work closely with our clients so that we understand the intricacies of each project. This allows us to work in harmony the surrounding area to create truly stunning projects that will stand the test of time.</p>
      </article>
      <figure class="contain-image-welcome"></figure>
    </section>
    <section id="small-team">
      <div class="hover-small-team"></div>
      <article class="contain-text-small-team">
        <h2>Small team, big ideas</h2>
        <router-link to="/about" class="btn-1">About Us<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></router-link>
      </article>
    </section>
    <section id="featured">
      <header>
        <h2>Featured</h2>
        <router-link to="/portfolio" class="btn-1">See All<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></router-link>
      </header> 
      <body class="contain-featured">
        <Featured number="1" title="Project Del Sol" class="featured-project-del-sol"/>
        <Featured number="2" title="228B Tower" class="featured-tower"/>
        <Featured number="3" title="Le Prototype" class="featured-prototype"/>
      </body>     
        <router-link to="/portfolio" class="btn-1 btn-mobile">See All<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></router-link>
    </section>
  </div>
</template>

<script>
import Header from './../components/Home/Header'
import Featured from './../components/Home/Featured'

// import { TweenMax } from 'gsap'
// import 'ScrollToPlugin'

export default {
  name: 'Home',
  components: {
    Header,
    Featured
  },
  mounted () {
    const scene2 = this.$scrollmagic.scene({
      triggerElement: '#welcome',
      triggerHook: 0.9,
      duration: 500
    }).setTween('h1', {  
      css: { 
          transform: 'translateY("0px")',
          transition: 'transform .2s linear',
          color: '#EEEFF4'
      },
    })

    this.$scrollmagic.addScene(scene2)

    const scene3 = this.$scrollmagic.scene({
      triggerElement: '#welcome',
      triggerHook: 0.5,
      duration: 300
    }).setTween('.contain-image-welcome', {  
      css: { 
          transform: 'translateX("0")',
          transition: 'transform .2s linear',
      },
    })

    this.$scrollmagic.addScene(scene3)

    const scene4 = this.$scrollmagic.scene({
      triggerElement: '#small-team',
      triggerHook: 0.9,
      duration: 300
    }).setTween('#small-team', {  
      css: { 
          transform: 'scale(1)',
          transition: 'transform .2s linear'
      },
    })

    this.$scrollmagic.addScene(scene4)
  }

}
</script>

<style lang="scss" scoped>
$white: #FFF;
$black: #000;
  .home {
    #welcome {
      width: 1110px;
      height: 668px;
      margin: auto;
      display: flex;
      justify-content: flex-end;
      align-items: flex-end;
      position: relative;
      margin-top: 95px;
      h1 {
        position: absolute;
        margin: 0;
        top: 0;
        left: 0;
        z-index: 1;
        transform: translateY(-80px);
        color: #FFF;

      }
      .contain-text-welcome {
        width: 446px;
        height: 493px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        margin-right: 125px;
        h2, p {
          margin: 0;
        }
      }
      .contain-image-welcome {
        transform: translateX(-50px);
        margin: 0;
        width: 350px;
        height: 568px;
        background-image: url('./../../public/home/desktop/image-welcome.jpg');
      }
    
      @media screen and (max-width: 1110px) {
        width: 581px;
        height: 618px;
        margin-top: 74px;
        .contain-text-welcome {
          width: 572px;
          height: 443px;
          margin-right: 0;
          h2 {
            width: 446px;
          }
        }
        .contain-image-welcome {
          display: none;
        }
      }
      @media screen and (max-width: 750px) {
        width: 311px;
        height: 643px;
        margin-top: 72px;
        .contain-text-welcome {
          width: 310px;
          height: 575px;
          h2 {
            width: 311px;
          }
        }
        .contain-image-welcome, h1 {
          display: none;
        }
      }
    }

    #small-team {
      width: 1110px;
      height: 560px;
      background-image: url('./../../public/home/desktop/image-small-team.jpg');
      margin: 200px auto 0 auto;
      position: relative;
       transform: scale(0.8);
      .hover-small-team {
        width: 100%;
        height: 100%;
        background-color: $black;
        position: absolute;
        opacity: 0.5;
      }
      .contain-text-small-team {
        width: 445px;
        height: 224px;
        position: absolute;
        top: 168px;
        left: 190px;
        h2 {
          width: 445px;
          color: $white;
        }
        a {
          width: 187px;
          svg {
            margin-left: 24px;
          }
        }
      }
      @media screen and (max-width: 1110px) {
        width: 573px;
        height: 560px;
        background-image: url('./../../public/home/tablet/image-small-team.jpg');
        .contain-text-small-team {
          left: 58px;
        }
      }
      @media screen and (max-width: 750px) {
        width: 375px;
        background-image: url('./../../public/home/mobile/image-small-team.jpg');
         .contain-text-small-team {
           width: 311px;
          left: 32px;
          h2 {
            width: 311px;
          }
        }
      }
    }

    #featured {
      width: 1110px;
      height: 696px;
      margin: auto;
      margin-top: 200px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      header {
        height: 72px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        .btn-1 {
          width: 169px;
        }
        a svg {
          margin-left: 24px;
        }
      }
      .contain-featured {
        width: 1110px;
        height: 560px;
        display: flex;
        justify-content: space-between;
        figure {
          background-repeat: no-repeat;
          background-size: cover;
        }
        .featured-project-del-sol {
          background-image: url('./../../public/portfolio/desktop/image-del-sol.jpg');
        }
        .featured-tower {
          background-image: url('./../../public/portfolio/desktop/image-228b.jpg');
        }
        .featured-prototype {
          background-image: url('./../../public/portfolio/desktop/image-prototype.jpg');
        }
      }

      .btn-mobile {
        display: none;
      }
      @media screen and (max-width: 1110px) {
        width: 573px;
        height: 925px;
        .contain-featured {
          flex-direction: column;
          width: 100%;
          height: 768px;
          .featured-project-del-sol {
            background-image: url('./../../public/portfolio/tablet/image-del-sol.jpg');
          }
          .featured-tower {
            background-image: url('./../../public/portfolio/tablet/image-228b.jpg');
          }
          .featured-prototype {
            background-image: url('./../../public/portfolio/tablet/image-prototype.jpg');
          }
        }
      }

      @media screen and (max-width: 415px) {
        width: 311px;
        height: 925px;
        header {
          a {
            display: none;
          }
        }
        .contain-featured {
          flex-direction: column;
          width: 100%;
          height: 768px;
          .featured-project-del-sol {
            background-image: url('./../../public/portfolio/tablet/image-del-sol.jpg');
          }
          .featured-tower {
            background-image: url('./../../public/portfolio/tablet/image-228b.jpg');
          }
          .featured-prototype {
            background-image: url('./../../public/portfolio/tablet/image-prototype.jpg');
          }
        }
        .btn-mobile {
          display: flex;
          width: 311px;
          margin-top: 20px;
          svg {
            margin-left: 24px;
          }
        }
      }
    }
  }

</style>
