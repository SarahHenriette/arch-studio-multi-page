<template>
    <div class="contact">
        <Header title="Tell us about your project" 
        section="Contact" 
        text="We’d love to hear more about your project. Please, leave a message below or give us a call. We have two offices, one in Texas and one in Tennessee. If you find yourself nearby, come say hello!">
            <template v-slot:image-header><div class="contain-image-header"></div></template>
        </Header>
        <section id="contact-details">
            <h2>Contact Details</h2>
            <div class="contain-text-contact-details">
                <div class="contain-text-office main-office">
                    <p class="title">Main Office</p>
                    <div class="infos">
                        <p>Mail: archone@mail.com</p>
                        <p>Address: 1892  Chenoweth Drive TN</p>
                        <p>Phone: 123-456-3451</p>
                    </div>
                    <p class="view-map">View on Map <svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#1B1D23" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></p>
                </div>
                <div class="contain-text-office office-II">
                    <p class="title">Office II</p>
                    <div class="infos">
                        <p>Mail: archtwo@mail.com</p>
                        <p>Address: 3399  Wines Lane TX</p>
                        <p>Phone: 832-123-4321</p>
                    </div>
                    <p class="view-map">View on Map <svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#1B1D23" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></p>
                </div>
            </div>
        </section>

        <div id="map"></div>

        <section id="connect-with-us">
            <h2>Connect with us</h2>
            <form>
                <input type="text" name="name" id="name" placeholder="Name">
                <input type="email" name="email" id="email" placeholder="Email">
                <textarea name="message" id="message" cols="30" rows="10" placeholder="Message"></textarea>
                <div class="btn-2"><svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></div>
            </form>
        </section>

    </div>
</template>


<script>
import Header from './../components/HeaderAboutContact'

export default {
    components: {
        Header
    },
    mounted () {
        const scene2 = this.$scrollmagic.scene({
            triggerElement: '#map',
            triggerHook: 0.8,
            duration: 500
            }).setTween('#map', {  
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

    .contact {
        header {
            .contain-image-header {
                background-image: url('../../public/contact/desktop/image-hero.jpg');
            }
        }

        #contact-details {
            width: 1110px;
            height: 205px;
            display: flex;
            justify-content: space-between;
            margin: 275px auto 0 auto; 
            h2, p {
                margin: 0;
            }
            h2 {
                width: 350px;
            }
            .contain-text-contact-details {
                width: 730px;
                height: 205px;
                display: flex;
                justify-content: space-between;
                .contain-text-office {
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    width: 350px;
                    .title {
                        font-weight: 700;
                    }
                    .infos {
                        height: 105px;
                        display: flex;
                        flex-direction: column;
                        justify-content: space-between;
                    }
                    .view-map {
                        color: $veryDarkBlue;
                        font-weight: bold;
                        display: flex;
                        align-items: center;
                        cursor: pointer;
                        text-decoration: none;
                        transition: text-decoration .5s linear;
                        &:hover {
                            text-decoration: underline;
                        } 
                        svg {
                            margin-left: 24px;
                        }
                    }
                }
            }
        }

        #map {
            width: 1110px;
            height: 560px;
            margin: auto;
            margin-top: 200px;
            background-image: url('../../public/contact/desktop/image-map.png');
            transform: scale(0.5);
        }

        #connect-with-us {
            width: 1110px;
            height: 348px;
            display: flex;
            justify-content: space-between;
            margin: auto;
            margin-top: 200px;
            h2 {
                margin: 0;
                width: 350px;
            }
            form {
                width: 730px;
                height: 100%;
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                position: relative;
                input {
                    height: 47px;
                }
                textarea {
                    height: 94px;
                }
                input, textarea {
                    width: 100%;
                    &:focus {
                        outline: none;
                    }
                    border: none;
                    border-bottom: solid 1px $veryDarkBlue;
                }
                .btn-2 {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    position: absolute;
                    bottom: -80px;
                    right: 0;
                }
            }
        }
    }

    @media screen and (max-width: 1110px) {
        .contact {
            #contact-details {
                width: 573px;
                height: 457px;
                flex-direction: column;
                h2 {
                    width: 573px;
                }
                .contain-text-contact-details {
                    width: 573px;
                    height: 350px;
                    flex-direction: column;
                    .contain-text-office {
                        width: 573px;
                        height: 148px;
                        position: relative;
                        .view-map {
                            position: absolute;
                            right: 0;
                            top: 84px;
                        }
                    }
                }
            }
            #map {
                width: 572px;
                background-image: url('../../public/contact/tablet/image-map.png');
            }

            
        #connect-with-us {
            width: 573px;
            height: 469px;
            flex-direction: column;
            h2 {
                margin: 0;
                width: 100%;
            }
            form {
                width: 573px;
                height: 349px;
            }
        }
        }
    }
    @media screen and (max-width: 750px) {
        .contact{
            header {
                .contain-image-header {
                background-image: url('../../public/contact/mobile/image-hero.jpg');
                }
            }

            #contact-details {
                width: 311px;
                height: 560px;
                flex-direction: column;
                margin-top: 72px;
                h2 {
                    width: 311px;
                }
                .contain-text-contact-details {
                    width: 311px;
                    height: 418px;
                    .contain-text-office {
                        width: 311px;
                        height: 189px; 
                        .view-map {
                            position: initial;
                        }  
                    }
                }
            }

            #map {
                width: 100%;
                height: 367px;
                margin-top: 72px;
                background-image: url('../../public/contact/mobile/image-map.png');
            }

            #connect-with-us {
                width: 311px;
                height: 493px;
                margin-top: 72px;
                h2 {
                    margin: 0;
                    width: 170px;
                }
                form {
                    width: 311px;
                    height: 349px;
                }
            }
        }
    }
</style>