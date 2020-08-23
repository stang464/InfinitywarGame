<template>
<div id="AttackButton">
    <button @click="$attk">Attack</button>
    <button @click="$Spattk">Special Attack</button>
</div>
</template>

<script>
export default {
    el: '#AttackButton',
    data: function () {
        return {
            
        };
    },

    props: {
        lable: String
    },

    methods:{
        randomDamage: function (min, max) {
            
            return Math.max(Math.floor(Math.random() * max) + 1, min)
            
           
        },
        $attk : function (){
            this.atk = this.randomDamage(3,10)
            this.$emit("atk",this.atk)
            console.log("Attack :",this.atk)
        },

        $Spattk : function (){
            this.spatk = this.randomDamage(10,20)
            this.$emit("spatk",this.spatk)
            console.log("Special Attack :",this.spatk)
        },
        
        
    }

}
</script>

<style>

</style>
