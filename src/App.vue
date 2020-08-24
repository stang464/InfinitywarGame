<template>
<div id="app">
    <div class="row">
        <div class="col-md-4"></div>
        <div class="col-md-4"> <button @click="show = !show">Start</button>

            <transition name="fade">
                <div v-if="show">
                    <Select @Imgmonster="imgmonster" @Imghero="imghero" @Heroname="Heroname" @HeroHP="HeroHp" @Monstername="Monstername" @MonsterHP="MonsterHP"></Select>
                </div>

            </transition>
        </div>

        <div class="col-md-4"></div>
    </div>
    <div class="row">
        <div class="col-md-4">

        </div>
        <div class="col-md-4">
            <AttackButton @atk="Attack" @SPATK="$SPAttack" @RandomATK="Attackback" @RandomSPATK="SPAttackback"> </AttackButton>
        </div>
        <div class="col-md-4">

        </div>
    </div>

    <div class="row">

        <div class="col-md-6">
            <h1>Hero : {{heroname}} | HP : {{HPHero}}</h1>
        </div>

        <div class="col-md-6">
            <h1>Monster : {{monstername}} | HP : {{HPMonster}}</h1>
        </div>

        <div class="row">
            <div class="col-md-12">
                <div v-if="HPHero <= 0" class="">
                    You Louse
                    Plaese Restart
                </div>
                <div v-if="HPMonster <= 0">
                    You WIN
                    Plaese Restart
                </div>

                <div v-if="HPMonster <= 0 && HPHero <= 0">
                    Draw
                    Plaese Restart
                </div>
            </div>

            
                

                
            
            

        </div>

    </div>
    <div class="row">
        <div class="col-md-6">
            <p v-if="imgHero"><img :src="imgHero" alt="" class="img-fluid image"></p>

        </div>

        <div class="col-md-6">
            <img src=imgMonster alt="">

        </div>

    </div>
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
            show: false,
            n: 0,
            HPHero: 0,
            heroname: "",
            monstername: "",
            HPMonster: 0,
            atk: 0,
            imgHero: '',
            imgMonster: ''

        }

    },
    methods: {

        Heroname(value) {
            this.heroname = value
            console.log("emit", this.heroname)
        },
        HeroHp(value) {
            this.HPHero = value
            console.log("emit", this.HPHero)
        },
        Monstername(value) {
            this.monstername = value
            console.log("emit m", this.monstername)
        },

        MonsterHP(value) {
            this.HPMonster = value
            console.log("emit mhp", this.HPMonster)
        },
        Attack(value) {
            this.atk = value
            this.HPMonster -= this.atk
        },

        $SPAttack(value) {
            this.atk = value
            this.HPMonster -= this.atk
        },
        Attackback(value) {
            this.atk = value
            this.HPHero -= this.atk
        },

        SPAttackback(value) {
            this.atk = value
            this.HPHero -= this.atk
        },

        imghero(value) {
            this.imgHero = value
            console.log(this.imgHero)

        },
        imgmonster(value) {
            this.imgMonster = value
        }

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

}

.fade-enter-active,
.fade-leave-active {
    transition: opacity .5s;
}

.fade-enter,
.fade-leave-to {
    opacity: 0;
}

.image {
    width: 500px;
    height: 400px;
}

</style>
