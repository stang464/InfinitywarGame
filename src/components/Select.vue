<template>
  <div id="Select">
     
      <button @click="random">
          random
      </button>

  </div>
</template>

<script>
export default {
    data: function(){
        return{
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
    methods :{
        pickName:function(n){
        
            console.log("name :" , this.player[n].name )
        },

        randomHero: function (min, max) {
            
            return Math.max(Math.floor(Math.random() * max) + 1, min)
            
           
        },

        random:function(){
            
            
            this.n = this.randomHero(0,3)
            this.name_hero = this.player[this.n].name 
            this.hp_hero = this.player[this.n].hp
            this.$emit("Heroname",this.name_hero)
            console.log("name :" ,this.name_hero)
            console.log("hp :" ,this.hp_hero)
            

        }
    }
    

}
</script>

<style>

</style>