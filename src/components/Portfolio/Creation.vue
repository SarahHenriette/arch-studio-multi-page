<template>
    <figure id="figure">
        <div class="opacity"></div>
        <div class="opacity2"></div>
        <caption>
            <p class="title">{{ name }}</p>
            <p>{{ date }}</p>
        </caption>
    </figure>
</template>

<script>
import { gsap } from "gsap";

export default {
    props: {
        name: String,
        date: String
    },
     mounted () {
        gsap.fromTo('figure', {scale: 0.5}, {scale: 1, duration: 0.5, ease: "linear"})
     }
}
</script>

<style lang="scss" scoped>
$white: #FFF;

    figure {
        width: 350px;
        height: 560px;
        position: relative;
        margin: 0;
        cursor: pointer;
        .opacity {
            background-color: #000;
            position: absolute;
            width: 100%;
            height: 100%;
            opacity: 0.2;
        }
        &:hover {
            .opacity2 {
                background-color: #000;
                position: absolute;
                width: 100%;
                height: 100%;
                opacity: 0.5;
            }
        }
        caption {
            width: 203px;
            height: 54px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: flex-start;
            position: absolute;
            bottom: 40px;
            left: 40px;
            p {
                color: $white!important;
                margin: 0;
            }
            .title {
                font-weight: bold;
            }
        }
    }

    @media screen and (max-width: 1110px) {
        figure {
            width: 573px;
            height: 240px;
            .h1-bis {
                top: 16px;
                right: 16px;
            }
        }
    }

    @media screen and (max-width: 415px) {
        figure {
            width: 311px;
            .h1-bis {
                display: none;
            }
            caption {
                bottom: 24px;
                left: 24px;
            }
        }
    }

</style>