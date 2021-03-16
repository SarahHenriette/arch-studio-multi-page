<template>
    <figure class="figure">
        <div class="opacity"></div>
        <p class="h1-bis">{{  number }}</p>
        <div class="caption">
            <p class="title">{{ title }}</p>
            <p>View All projects</p>
        </div>
    </figure>
</template>

<script>
export default {
    props: {
        number: String,
        title: String
    },
     mounted () {
        const scene2 = this.$scrollmagic.scene({
            triggerElement: '.figure',
            triggerHook: 0.7,
            duration: 500
            }).setTween('.h1-bis', {  
            css: { 
                transform: 'scale(1)',
                transition: 'transform .2s linear' ,
            },
        })

    this.$scrollmagic.addScene(scene2)
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
        .opacity {
            background-color: #000;
            position: absolute;
            width: 100%;
            height: 100%;
            opacity: 0.2;
        }
        .h1-bis {
            opacity: 0.5;
            position: absolute;
            right: 0;
            top: 32px;
            margin: 0;
            transform: scale(0.2);
        }
        .caption {
            width: 142px;
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
            .caption {
                bottom: 24px;
                left: 24px;
            }
        }
    }

</style>