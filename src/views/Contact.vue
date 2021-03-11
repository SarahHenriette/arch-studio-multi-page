<template>
    <div class="contact">
        <Header title="Tell us about your project" 
        section="Contact" 
        text="We’d love to hear more about your project. Please, leave a message below or give us a call. We have two offices, one in Texas and one in Tennessee. If you find yourself nearby, come say hello!">
            <template v-slot:image-header><div class="contain-image-header"></div></template>
        </Header>
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
    .contact {
        header {
            .contain-image-header {
                background-image: url('../../public/contact/desktop/image-hero.jpg');
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
        }
    }
</style>