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
        }
    }
</style>