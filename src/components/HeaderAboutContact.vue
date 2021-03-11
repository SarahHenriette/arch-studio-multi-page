<template>
    <header>
        <h1 class="h1-bis">{{ section }}</h1>
        <slot name="image-header"></slot>
        <div class="contain-text-header">
            <h2>{{ title }}</h2>
            <p>{{ text }}</p>
        </div>
    </header>
</template>

<script>
import { gsap } from "gsap";
export default {
    props: {
        title: String,
        text: String,
        section: String
    },
    mounted() {
        gsap.fromTo('.contain-image-header ', {x: -180}, {x: 0, duration: 1})
    },
}
</script>

<style lang="scss" scoped>
    header {
        width: 1110px;
        height: 720px;
        position: relative;
        margin: auto;
        h1 {
            right: 0;
            top: 117px;
            z-index: 10;
            margin: 0;
        }
        .contain-image-header {
            width: 635px;
            height: 100%;
            left: 0;
            background-repeat: no-repeat;
            background-size: cover;
        }
        .contain-text-header {
            width: 628px;
            height: 503px;
            right: 0;
            bottom: -1px;
            background-color: #FFF;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            align-items: flex-end;
            h2 {
                width: 446px;
                height: 133px;
                margin-top: 0;
                margin-bottom: 35px;
            }
            p {
                width: 445px;
                height: 100px;
                margin: 0;
            }
        }
        .contain-image-header, .contain-text-header, h1 {
            position: absolute;
        }
    }

    @media screen and (max-width: 1110px) {
        header {
            width: 573px;
            h1 {
                top: 189px;
            }
            .contain-image-header {
                width: 100%;
            }
            .contain-text-header {
                align-items: center;
                width: 572px;
                height: 431px;
                right: -57px;
            }
        }
    }

    @media screen and (max-width: 750px) {
        header {
            width: 100%;
            height: 533px;
            h1 {
                display: none;
            }
             .contain-image-header {
                 height: 240px;

             }
            .contain-text-header {
                width: 343px;
                height: 338px;
                right: 32px;
                h2 {
                    height: 96px;
                    margin-bottom: 12px;
                }
                p {
                    height: 150px;
                }
                h2, p {
                    width: 311px;
                }
            }
        }
    }
</style>