<template>
<div id="app">
    
    <button @click="show = !show">
        Start
    </button>
    <AttackButton/>
 
    <transition name="fade">
        <div v-if="show">
            Select
            
            
            <button >Ironman</button>
            
        </div>
    </transition>

    
</div>
</template>


<script>
import AttackButton from "./components/AttackButton.vue"

export default {
    name: 'App',

    components: {
        AttackButton
        
    },
    data: function () {
        return {
            show: true,
            n: 0,
            pick: String,
            player: [{
                    name: 'Anakin',
                    hp: 100,
                    image: ''
                },
                {
                    name: 'Ironman',
                    hp: 120,
                    image: ''
                },
                {
                    name: 'spiderman',
                    hp: 110,
                    image: ''
                },
                {
                    name: 'Star lord',
                    hp: 129,
                    image: ''
                },
            ],

        }

    },
    methods: {
        
        
    }

}
</script>



<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity .5s;
}

.fade-enter,
.fade-leave-to {
    opacity: 0;
}
</style>
