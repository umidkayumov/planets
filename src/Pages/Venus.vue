<template>
    <div id="venus" class="section">
        <DescriptionBody>
            <Image>
                <img class="" id="main_image" src="../assets/images/planets/venus.png" alt="Planet venus">
                <img class=" hidden_image" id="internal_image" src="../assets/images/planet-venus-internal.svg" alt="Planet venus">
                <img id="geology_image" class="hidden_image absolute" src="../assets/images/geology-venus.png" height="199" width="163" alt="Geology of venus">
            </Image>
            <Infos>
                <h1>{{ venus.name }}</h1>
                <p id="text">{{overview.content}}</p>
                <p class="source"><span>Source :</span> 
                    <a id="source" :href="overview.source" target="_blank">Wikipédia</a>
                    <img src="../assets/images/icon-source.svg" alt="Source arrow icon">
                </p>
            </Infos>
        </DescriptionBody>
        <Numbers>
            <Rotation>
                {{venus.rotation}}
            </Rotation>
            <Revolution>
                {{venus.revolution}}
            </Revolution>
            <Radius>
                {{venus.radius}}
            </Radius>
            <Temperature>
                {{venus.temperature}}
            </Temperature>
        </Numbers>
    </div>
    
</template>

<script>
import DescriptionBody from '../components/DescriptionBody.vue'
import Infos from '../components/Infos.vue'
import Image from '../components/Image.vue'
import Numbers from '../components/Numbers.vue'
import Rotation from '../components/Rotation.vue'
import Revolution from '../components/Revolution.vue'
import Radius from '../components/Radius.vue'
import Temperature from '../components/Temperature.vue'
export default {
    components: {
        DescriptionBody,
        Infos,
        Image,
        Numbers,
        Rotation,
        Revolution,
        Radius,
        Temperature
    },
    data() {
        return {
            venus: [],
            overview: [],
            geology: [],
            structure: [],
        }
    },
    created() {
        this.venus = this.$json.venus;
        this.overview = this.$json.venus.overview;
        this.geology = this.$json.venus.geology;
        this.structure = this.$json.venus.structure;
    },
    mounted() {
        var app = this;
        app.$functions.switchTopic(app);
        app.$functions.activeBtn();
    },
}
</script>