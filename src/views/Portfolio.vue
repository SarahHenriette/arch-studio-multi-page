<template>
    <div class="portfolio">
           <Creation v-for="creation in creations" :key="creation.id" :class="creation.className" :name="creation.name" :date="creation.date"/>
    </div>
</template>

<script>
import Creation from './../components/Portfolio/Creation'

export default {
    components: {
        Creation
    },
    data () {
        return {
            creations: [
                 {id:"01", name:"Seraph Station", date: "September 2019", className: "creation-seraph"},
                 {id:"02", name:"Eebox Building", date: "August 2017", className: "creation-eebox"},
                 {id:"03", name:"Federal II Tower", date: "March 2017", className: "creation-federal"},
                 {id:"04", name:"Project Del Sol", date: "January 2016", className: "creation-del-sol"},
                 {id:"05", name:"Le Prototype", date: "October 2015", className: "creation-prototype"},
                 {id:"06", name:"228B Tower", date: "April 2015", className: "creation-228b"},
                 {id:"07", name:"Grand Edelweiss Hotel", date: "December 2013", className: "creation-edelweiss"},
                 {id:"08", name:"Netcry Tower", date: "August 2012", className: "creation-netcry"},
                 {id:"09", name:"Hypers", date: "January 2012", className: "creation-hypers"},
                 {id:"10", name:"SXIV Tower", date: "March 2011", className: "creation-sxiv"},
                 {id:"11", name:"Trinity Bank Tower", date: "September 2010", className: "creation-trinity"},
                 {id:"12", name:"Project Paramour", date: "February 2008", className: "creation-paramour"},
                    
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    .portfolio {
        width: 1110px;
        height: 2336px;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        figure {
            background-repeat: no-repeat;
        }
        .creation-seraph {
            background-image: url('../../public/portfolio/desktop/image-seraph.jpg');
        }
        .creation-eebox {
            background-image: url('../../public/portfolio/desktop/image-eebox.jpg');
        }
        .creation-federal {
            background-image: url('../../public/portfolio/desktop/image-federal.jpg');
        }
        .creation-del-sol {
            background-image: url('../../public/portfolio/desktop/image-del-sol.jpg');
        }
        .creation-prototype {
            background-image: url('../../public/portfolio/desktop/image-prototype.jpg');
        }
        .creation-228b {
            background-image: url('../../public/portfolio/desktop/image-228b.jpg');
        }
        .creation-edelweiss {
            background-image: url('../../public/portfolio/desktop/image-edelweiss.jpg');
        }
        .creation-netcry {
            background-image: url('../../public/portfolio/desktop/image-netcry.jpg');
        }
        .creation-hypers {
            background-image: url('../../public/portfolio/desktop/image-hypers.jpg');
        }
        .creation-sxiv {
            background-image: url('../../public/portfolio/desktop/image-sxiv.jpg');
        }
        .creation-trinity {
            background-image: url('../../public/portfolio/desktop/image-trinity.jpg');
        }
        .creation-paramour {
            background-image: url('../../public/portfolio/desktop/image-paramour.jpg');
        }
    }

    @media screen and (max-width: 1110px) {
        .portfolio {
            width: 573px;
            height: 3120px;
            .creation-seraph {
                background-image: url('../../public/portfolio/tablet/image-seraph.jpg');
            }
            .creation-eebox {
                background-image: url('../../public/portfolio/tablet/image-eebox.jpg');
            }
            .creation-federal {
                background-image: url('../../public/portfolio/tablet/image-federal.jpg');
            }
            .creation-del-sol {
                background-image: url('../../public/portfolio/tablet/image-del-sol.jpg');
            }
            .creation-prototype {
                background-image: url('../../public/portfolio/tablet/image-prototype.jpg');
            }
            .creation-228b {
                background-image: url('../../public/portfolio/tablet/image-228b.jpg');
            }
            .creation-edelweiss {
                background-image: url('../../public/portfolio/tablet/image-edelweiss.jpg');
            }
            .creation-netcry {
                background-image: url('../../public/portfolio/tablet/image-netcry.jpg');
            }
            .creation-hypers {
                background-image: url('../../public/portfolio/tablet/image-hypers.jpg');
            }
            .creation-sxiv {
                background-image: url('../../public/portfolio/tablet/image-sxiv.jpg');
            }
            .creation-trinity {
                background-image: url('../../public/portfolio/tablet/image-trinity.jpg');
            }
            .creation-paramour {
                background-image: url('../../public/portfolio/tablet/image-paramour.jpg');
            }
        }
    }

        @media screen and (max-width: 600px) {
        .portfolio {
            width: 311px;
            .creation-seraph {
                background-image: url('../../public/portfolio/mobile/image-seraph.jpg');
            }
            .creation-eebox {
                background-image: url('../../public/portfolio/mobile/image-eebox.jpg');
            }
            .creation-federal {
                background-image: url('../../public/portfolio/mobile/image-federal.jpg');
            }
            .creation-del-sol {
                background-image: url('../../public/portfolio/mobile/image-del-sol.jpg');
            }
            .creation-prototype {
                background-image: url('../../public/portfolio/mobile/image-prototype.jpg');
            }
            .creation-228b {
                background-image: url('../../public/portfolio/mobile/image-228b.jpg');
            }
            .creation-edelweiss {
                background-image: url('../../public/portfolio/mobile/image-edelweiss.jpg');
            }
            .creation-netcry {
                background-image: url('../../public/portfolio/mobile/image-netcry.jpg');
            }
            .creation-hypers {
                background-image: url('../../public/portfolio/mobile/image-hypers.jpg');
            }
            .creation-sxiv {
                background-image: url('../../public/portfolio/mobile/image-sxiv.jpg');
            }
            .creation-trinity {
                background-image: url('../../public/portfolio/mobile/image-trinity.jpg');
            }
            .creation-paramour {
                background-image: url('../../public/portfolio/mobile/image-paramour.jpg');
            }
        }
    }
</style>