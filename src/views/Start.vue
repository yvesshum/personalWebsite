<template>
<div class="start">
    <el-row :gutter="20" type="flex" class="row-bg">
        <el-col :span="18"> 
            <fade-transition>
                <h1 v-if="ready">Yves Shum</h1>
            </fade-transition>
            
            <fade-transition :delay="1000">
                <h2 v-if="ready" >Welcome to my website</h2>
            </fade-transition>
            
        </el-col>
        <el-col :span="6">
            <fade-transition :duration="100" :delay="2000">
                <div v-if="button" >
                    <el-card style="background-color: #121212; border-weight: 0">
                        <font-awesome-icon icon="chevron-right"  color="#FFFFFF"/>
                        <h1>Continue</h1>
                    </el-card>
                </div> 
            </fade-transition>
            
        </el-col>
    </el-row>

</div>
</template>

<script>
import {FadeTransition} from 'vue2-transitions'


export default {
    
    name: 'Start',
    data() {
        return {
            ready: false,
            button: false
        }
    },
    methods: {
        handleContinueClicked() {
            console.log('cicked')
        },
    },
    mounted() {
        this.ready = true;
        this.button = true;
    },
    components: {
        FadeTransition,
        // SlideXRightTransition
    }
}
</script>


<style lang='scss'>
    .start {
        color:floralwhite;
        display: flex;
        align-items: center;
        width: 100%;
        flex: 1;
        margin-right: 50
    }
    .fade-enter-active, .fade-leave-active {
        transition: opacity 1s;
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
    }
    h1 {
        color: #FFFFFF;
    }
    .row-bg {
        width: 90%;
        
    }

</style>
