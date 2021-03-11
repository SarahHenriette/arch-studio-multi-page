<template>
    <transition name="fade" mode="out-in">
    <div class="slide" >
        <div class="contain-text">
            <h1><slot name="title"></slot></h1>
            <p><slot name="text"></slot></p>
            <router-link to="/portfolio" class="btn-1">See Our Portfolio<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></router-link>
        </div>
    </div>
    </transition>
</template>
    

<script>
// import { gsap } from "gsap";

    export default {
        props: {
            title: String,
            text: String
        },
        mounted() {
            // gsap.fromTo('.slide', {x: -80}, {y: 0, duration: 1})
        },
    }
</script>


<style lang="scss" scoped>
$white: #FFF;

    .slide {
        width: 100%;
        height: 100%;
        // display: none;
        background-repeat: no-repeat;
        background-size: cover;
        position: absolute;
         transform: translateX(1110px);
        //  z-index: 200;
        .contain-text {
            padding-top: 180px;
            margin-left: 190px;
            h1, p {
                color: $white!important;
            }
            h1 {
                margin: 0;
                width: 544px;
                height: 160px;
            }
            p {
                width: 445px;
                height: 75px;
                margin-top: 14px;
                margin-bottom: 40px;
            }
            .btn-1 {
                width: 252px;
                svg {
                    margin-left: 24px;
                }
            }
        }
    }
    .fade-enter-active, .fade-leave-active {
  transition: 0.3s opacity ease;
}

.fade-enter, .fade-leave-active {
  opacity: 0
}

    @media screen and (max-width: 1110px) {
        .slide {
            .contain-text {
                margin: auto;
                width: 457px;
                height: 361px;
            }
        }
    }

    @media screen and (max-width: 750px) {
        .slide {
            .contain-text {
                margin: auto;
                padding-top: 110px;
                width: 311px;
                height: auto;
                h1 , p{
                    width: 311px;
                }

                h1 {
                    height: 96px;
                }
                p {
                    height: auto;
                }
            }
        }
    }
</style>