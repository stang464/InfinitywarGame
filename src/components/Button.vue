<template>
<div id="demo">
    <button @click="show = !show">
        Start
    </button>
    <transition name="fade">
        <div v-if="show" >
            Select 
             <button @click="pick_anakin">Anakin</button>
             <button>Ironman</button>
             <button>Spiderman</button>
             <button>Dr.Strange</button>
             <button>Thor</button>
             <button>Captain American</button>
             <button>Blackwidow</button>
             <button>Hawkeye</button>
             <button>Random</button>
             

        </div>
       
    </transition>
</div>
</template>

<script>
export default {
    el: '#demo',
    data: function () {
        return {
            show: true
        };
    },

    props: {
        lable: String
    },

    methods:{
        pick_anakin(){
            this.mgs = 'Anakin';
        }
        
    }

}
</script>

<style>

</style>
