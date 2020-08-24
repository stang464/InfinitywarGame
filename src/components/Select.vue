<template>
<div id="Select">

    <button @click="random">
        random
    </button>

</div>
</template>

<script>
export default {
    data: function () {
        return {
            player: [{
                    name: 'Anakin',
                    hp: 106,
                    image: 'https://www.google.com/url?sa=i&url=https%3A%2F%2Ftenor.com%2Fsearch%2Fanakin-skywalker-i-hate-you-gifs&psig=AOvVaw1uxM4moInDFKJJwK9LfWLl&ust=1598339568992000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCLDLsoWls-sCFQAAAAAdAAAAABAD'
                },
                {
                    name: 'Ironman',
                    hp: 120,
                    image: 'https://i.pinimg.com/originals/fe/cb/f8/fecbf8a7a6a40abf01c1762d33261c50.gif'
                },
                {
                    name: 'spiderman',
                    hp: 110,
                    image: 'https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/c9be30e5-5d79-4c7e-b734-3ce0a28bb294/d9v33ow-f1b00729-ae43-443c-a5d7-2a5113590301.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvYzliZTMwZTUtNWQ3OS00YzdlLWI3MzQtM2NlMGEyOGJiMjk0XC9kOXYzM293LWYxYjAwNzI5LWFlNDMtNDQzYy1hNWQ3LTJhNTExMzU5MDMwMS5naWYifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.wDP60l2_VRv5FQAYbYJTPzxe9uBgHh0ot6QDvevoQZk'
                },
                {
                    name: 'Star lord',
                    hp: 129,
                    image: 'https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/26082c6d-0264-4f85-85ab-5182ed9e8421/d9ssic0-025ae545-b5fa-46d6-8728-c6fb44c79207.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvMjYwODJjNmQtMDI2NC00Zjg1LTg1YWItNTE4MmVkOWU4NDIxXC9kOXNzaWMwLTAyNWFlNTQ1LWI1ZmEtNDZkNi04NzI4LWM2ZmI0NGM3OTIwNy5naWYifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.sjpoRgzUJ-l22HoyD-B6R1XS5Aa2TVDbs2i33eD1yL0'
                },
            ],

            monster: [{
                    name: 'Darth Vader',
                    hp: 140,
                    image: ''
                },
                {
                    name: 'Thnos',
                    hp: 126,
                    image: ''
                },
                {
                    name: 'Red Skull',
                    hp: 110,
                    image: ''
                },
                {
                    name: 'Kingpin',
                    hp: 108,
                    image: ''
                },
                {
                    neme: 'Loki',
                    hp: 114,
                    image: ''
                },
                {
                    name: 'Ultron',
                    hp: 134,
                    image: ''
                }
            ]
        }
    },
    methods: {
        pickName: function (n) {

            console.log("name :", this.player[n].name)
        },

        randomHero: function (min, max) {

            return Math.max(Math.floor(Math.random() * max) + 1, min)

        },

        random: function () {
            this.nH = this.randomHero(0, 3)
            this.nM = this.randomHero(0, 5)
            this.name_hero = this.player[this.nH].name //สุ่ม hero เก็บในตัวแปร ชื่อ
            this.hp_hero = this.player[this.nH].hp //สุ่ม hero เก็บในตัวแปร hp

            this.name_monster = this.monster[this.nM].name //สุ่ม moster เก็บในตัวแปร ชื่อ
            this.hp_monster = this.monster[this.nM].hp

            this.$emit("Heroname", this.name_hero)
            this.$emit("HeroHP", this.hp_hero)

            this.$emit("Monstername", this.name_monster)
            this.$emit("MonsterHP", this.hp_monster)

            console.log("name :", this.name_hero)
            console.log("hp :", this.hp_hero)

            console.log("name :", this.name_monster)
            console.log("hp :", this.hp_monster)

            this.imghero = this.player[this.nH].image
            
            this.$emit("Imghero",this.imghero)
          //  this.$emit("Imgmonster", this.imgmonster)
        }
    },

}
</script>

<style>

</style>
