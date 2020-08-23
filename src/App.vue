<template>
<div id="app">
    
    <button @click="show = !show">
        Start
    </button>
    
 
    <transition name="fade">
        <div v-if="show">
            Select
            
            
            <Select></Select>
            
        </div>
        
    </transition>

    <AttackButton/>

    
</div>
</template>


<script>
import AttackButton from "./components/AttackButton.vue"
import Select from "./components/Select.vue"

export default {
    name: 'App',

    components: {
        AttackButton,
        Select
        
    },
    data: function () {
        return {
            show: true,
            n: 0,
            pick: String,
            

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
