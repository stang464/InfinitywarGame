<template>
  <div id="Select">
      <button @click="pickName(0)">
          Anakin
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
            this.$emit("Name" ,this.player[0].name)
            console.log("name :" , this.player[n].name )
        }
    }
    

}
</script>

<style>

</style>