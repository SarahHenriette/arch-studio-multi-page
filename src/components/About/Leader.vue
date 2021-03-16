<template>
    <div class="profile-leaders">
        <figure id="photo" class="photo">
            <slot name="img"></slot>
            <div class="opacity">
                <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40"><path fill="#FFF" d="M36 0H4C1.8 0 0 1.8 0 4v32c0 2.2 1.8 4 4 4h32c2.2 0 4-1.8 4-4V4c0-2.2-1.8-4-4-4zM12 34H6V16h6v18zM9 12.6C7 12.6 5.4 11 5.4 9S7 5.4 9 5.4 12.6 7 12.6 9 11 12.6 9 12.6zM34 34h-6V23.4c0-1.6-1.4-3-3-3s-3 1.4-3 3V34h-6V16h6v2.4c1-1.6 3.2-2.8 5-2.8 3.8 0 7 3.2 7 7V34z"/></svg>
                <svg xmlns="http://www.w3.org/2000/svg" width="40" height="33"><path fill="#FFF" d="M40 4.262a16.384 16.384 0 01-4.713 1.291 8.22 8.22 0 003.608-4.54 16.44 16.44 0 01-5.212 1.992 8.193 8.193 0 00-5.99-2.592c-5.298 0-9.191 4.944-7.995 10.075C12.88 10.147 6.833 6.88 2.785 1.915.635 5.603 1.67 10.428 5.323 12.872a8.172 8.172 0 01-3.715-1.027c-.09 3.802 2.635 7.358 6.582 8.15a8.225 8.225 0 01-3.707.14 8.213 8.213 0 007.667 5.698A16.5 16.5 0 010 29.233a23.232 23.232 0 0012.58 3.687c15.237 0 23.845-12.868 23.325-24.41A16.708 16.708 0 0040 4.262z"/></svg>
            </div>
        </figure>
        <caption>
            <p class="name">{{ name }}</p>
            <p class="job">{{ job }}</p>
        </caption>
        <div class="reseau-tablet">
            <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40"><path fill="#1B1D23" d="M36 0H4C1.8 0 0 1.8 0 4v32c0 2.2 1.8 4 4 4h32c2.2 0 4-1.8 4-4V4c0-2.2-1.8-4-4-4zM12 34H6V16h6v18zM9 12.6C7 12.6 5.4 11 5.4 9S7 5.4 9 5.4 12.6 7 12.6 9 11 12.6 9 12.6zM34 34h-6V23.4c0-1.6-1.4-3-3-3s-3 1.4-3 3V34h-6V16h6v2.4c1-1.6 3.2-2.8 5-2.8 3.8 0 7 3.2 7 7V34z"/></svg>
            <svg xmlns="http://www.w3.org/2000/svg" width="40" height="33"><path fill="#1B1D23" d="M40 4.262a16.384 16.384 0 01-4.713 1.291 8.22 8.22 0 003.608-4.54 16.44 16.44 0 01-5.212 1.992 8.193 8.193 0 00-5.99-2.592c-5.298 0-9.191 4.944-7.995 10.075C12.88 10.147 6.833 6.88 2.785 1.915.635 5.603 1.67 10.428 5.323 12.872a8.172 8.172 0 01-3.715-1.027c-.09 3.802 2.635 7.358 6.582 8.15a8.225 8.225 0 01-3.707.14 8.213 8.213 0 007.667 5.698A16.5 16.5 0 010 29.233a23.232 23.232 0 0012.58 3.687c15.237 0 23.845-12.868 23.325-24.41A16.708 16.708 0 0040 4.262z"/></svg>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        name: String,
        job: String,
    },
    mounted () {
        const scene2 = this.$scrollmagic.scene({
            triggerElement: '.profile-leaders',
            triggerHook: 0.8,
            duration: 500
            }).setTween('.photo', {  
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
$veryDarkBlue: #1B1D23;

    .profile-leaders {
        width: 350px;
        height: 398px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        figure {
            margin: 0;
            width: 100%;
            height: 320px;
            transform: scale(0.7);
            cursor: pointer;
            position: relative;
            transition: all .5s linear;
            .opacity {
                position: absolute;
                top: 0;
                width: 100%;
                height: 100%;
                opacity: 0.5;
                background-color: transparent;                
                transition: all .5s linear;
                svg {
                    margin: 0 15px;
                    display: none;
                }
            }
            &:hover {
                .opacity {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    background-color: $veryDarkBlue;
                    svg {
                        display: block;
                    }
                }
            }
        }
        caption {
            width: 100%;
            height: 54px;
            p {
                margin: 0;
                text-align: left;
            }
            .name {
                font-weight: bold;
                font-size: 18px!important;
            }
        }
        .reseau-tablet {
            display: none;
        }
    }

    @media screen and (max-width: 1110px) {
        .profile-leaders {
            width: 281px;
            height: 374px;
            figure {
                height: 256px;
                img {
                    width: 100%;
                }
            }
            .reseau-tablet {
                display: flex;
                height: 32px;
                align-items: center;
                svg {
                    margin-right: 25px;
                }
            }

        }
    }

    @media screen and (max-width: 600px) {
        .profile-leaders {
            width: 311px;
            height: 402px;
            figure {
                height: 284px;
                img {
                    width: 100%;
                }
            }
        }
    }
</style>