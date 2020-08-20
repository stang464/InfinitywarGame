<template>
<div id="app">
    <Button></Button>
    
</div>


</template>


<script>
import Button from './components/Button.vue'
export default {

    name: 'App',
    
    components: {
      Button
    },
    data: function () {
        return {
            player: [{
                    name: 'Anakin',
                    hp: 100,
                    image: ''},
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
                    name: 'stat lord',
                    hp: 129,
                    image: ''
                },
            ],
            
        }

    },

   

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
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>
