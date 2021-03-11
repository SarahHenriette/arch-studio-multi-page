<template>
    <footer>
        <div class="contain-logo-footer">
            <Logo color="#FFF"/>
        </div>
        <div class="contain-links-footer">
            <ul class="links-footer">
                <li><router-link to="/portfolio">Portfolio</router-link></li>
                <li><router-link to="/about">About Us</router-link></li>
                <li><router-link to="/contact">Contact</router-link></li>
            </ul>
        </div>
        <router-link to="/portfolio" class="btn-1 btn-footer">See Our Portfolio<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"/></g></svg></router-link>
    </footer>
</template>

<script>
import Logo from './Logo'
export default {
    
    components: {
        Logo
    }
}
</script>

<style lang="scss" scoped>
$veryDarkBlue: #1B1D23;
$veryLightGrey: #EEEFF4;
footer {
    width: 1110px;
    height: 200px;
    display: flex;
    position: relative;
    margin: auto;
    margin-top: 160px;
    .contain-logo-footer {
        width: 200px;
        height: 100%;
        background-color: $veryDarkBlue;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .contain-links-footer {
        width: 784px;
        height: 100%;
        background-color: $veryLightGrey;
        .links-footer {
            margin: 87px 0 88px 85px;
            width: 316px;
            height: 25px;
            display: flex;
            justify-content: space-between;
            li a {
                padding: 15px;
            }
        }
    }
    .btn-1 {
        width: 252px;
        position: absolute;
        right: 0;
        top: 64px;
        svg {
            margin-left: 24px;
        }
    }
}

@media screen and (max-width: 1110px){
    footer {
        width: 768px;
        height: 120px;
        .contain-logo-footer {
            width: 120px;
        }
        .contain-links-footer {
            width: 492px;
            .links-footer {
                margin: 48px 0 47px 40px;
            }
        }
        .btn-1 {
            top: 24px;
        }
    }
}

@media screen and (max-width: 750px) {
    footer {
        width: 100%;
        height: 443px;
        flex-direction: column;
        .contain-logo-footer {
            height: 120px;
            position: absolute;
            top: 0;
            z-index: 10;
            left: 0;
            right: 0;
            margin: auto;
        }
        .contain-links-footer {
            width: 100%;
            height: 383px;
            position: absolute;
            top: 60px;
            margin: auto;
            .links-footer {
                width: 75px;
                height: 139px;
                flex-direction: column;
                margin: 92px auto 0 auto; 
            }
            .links-footer li a  {
                padding: 0;
            }
        }
        .btn-1 {
            top: auto;
            bottom: 48px;
            left: 0;
            right: 0;
            margin: auto;
        }
    }
}
</style>