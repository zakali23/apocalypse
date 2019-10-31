<template>
    <v-app>
        <br><br>
        <template v-if="choix">
            <h1  class="text-sm-center text--white">Mes choix :</h1><br>
            <v-layout >
                <v-flex md4  v-if="res1" class="text-sm-center bordure">
                    <img :src="movie.img" :height="choixht" width="auto" style="border : 5px solid white !important;
"/><br>
                    <span>{{movie.name}}</span>
                </v-flex>

                <v-flex md4  v-if="res2" class="text-sm-center bordure">
                    <img :src="drink.img" :height="choixht" width="auto"  style="border : 5px solid white !important;
"/><br>
                    <span> {{drink.name}}</span>
                </v-flex>

            </v-layout>
        </template>
        <template v-if="movie.show">
            <h1  class="text-sm-center">Les Films secrets</h1><br>
            <v-layout v-if="movie.show">
                <v-flex md-3 @click.once="view1" v-if="movie.view1" class="text-sm-center">
                    <img :src="movie.img" :height="ht" width="auto" /><br>
                    {{movie.name}}
                </v-flex>
                <v-flex md-3 @click.once="view2" v-if="movie.view2" class="text-sm-center">
                    <img :src="movie.img" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click.once="view3" v-if="movie.view3" class="text-sm-center">
                    <img :src="movie.img" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click.once="view4" v-if="movie.view4" class="text-sm-center">
                    <img :src="movie.img" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click.once="view5" v-if="movie.view5" class="text-sm-center">
                    <img :src="movie.img" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click.once="view6" v-if="movie.view6" class="text-sm-center">
                    <img :src="movie.img" :height="ht" width="auto" />
                </v-flex>
            </v-layout>
        </template>
        <template v-if="drink.show">
            <h1  class="text-sm-center">Les boissons en sang</h1>
            <v-layout drink>
                <v-flex md-3 @click.once="view7" v-if="drink.view1" class="text-sm-center carteCocktail">
                    <img :src="drink.img" :height="ht" width="auto" /><br>
                    {{drink.name}}
                </v-flex>
                <v-flex md-3 @click.once="view8" v-if="drink.view2" class="text-sm-center carteCocktail">
                    <img :src="drink.img" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click.once="view9" v-if="drink.view3" class="text-sm-center carteCocktail">
                    <img :src="drink.img" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click.once="view10" v-if="drink.view4" class="text-sm-center carteCocktail">
                    <img :src="drink.img" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click.once="view11" v-if="drink.view5" class="text-sm-center carteCocktail">
                    <img :src="drink.img" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click.once="view12" v-if="drink.view6" class="text-sm-center carteCocktail">
                    <img :src="drink.img" :height="ht" width="auto" />
                </v-flex>
            </v-layout>
        </template>


    </v-app>

</template>

<script>
    import axios from 'axios';
    import 'vuetify/dist/vuetify.min.css'
    import '@mdi/font/css/materialdesignicons.css'
    import search from './components/search.vue'
    export default {
        name: "HelloWorld",
        components:{
            search
        },
        data: () => ({
            choixht:200,
            ht:280,
            name:'',
            nameErrors:'',
            number:'',
            lettre:'',
            movies:[],
            rotation:'cont',
            res1:false,
            res2:false,
            res3:false,
            movie:{
                show:true,
                view1:true,
                view2:true,
                view3:true,
                view4:true,
                view5:true,
                view6:true,
                img:"/images/carte.png/",
                name:''
            },
            drink:{
                show:false,
                view1:true,
                view2:true,
                view3:true,
                view4:true,
                view5:true,
                view6:true,
                img:"/images/carte.png/",
                name:''
            },
            bouffe:{
                img:'/images/bouffe/'
            },
            choix:false


        }),
        methods: {

            view1 () {

                this.movie.view2 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.res1 = true
                this.number = this.getRandomInt()
                this.getResultMovie()
            },
            view2 () {

                this.movie.view1 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.res1 = true
                this.getResultMovie()

            },
            view3 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.res1 = true
                this.getResultMovie()
            },
            view4 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.movie.view3 = false
                this.res1 = true
                this.getResultMovie()
            },
            view5 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view4 = false
                this.movie.view6 = false
                this.movie.view3 = false
                this.res1 = true
                this.getResultMovie()
            },
            view6 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view5 = false
                this.movie.view4 = false
                this.movie.view3 = false
                this.res1 = true
                this.getResultMovie()
            },
            view7 () {
                this.res2 = true
                this.drink.view2 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view6 = false
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
            },
            view8 () {
                this.res2 = true
                this.drink.view1 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view6 = false

                this.lettre = this.getRandomLettre()
                this.getResultDrink()
            },
            view9 () {
                this.res2 = true
                this.drink.view2 = false
                this.drink.view1 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view6 = false
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
            },
            view10 () {
                this.res2 = true
                this.drink.view2 = false
                this.drink.view3 = false
                this.drink.view1 = false
                this.drink.view5 = false
                this.drink.view6 = false
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
            },
            view11 () {
                this.res2 = true
                this.drink.view2 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view1 = false
                this.drink.view6 = false
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
            },
            view12 () {
                this.res2 = true
                this.drink.view1 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view2 = false
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
            },
            getRandomInt() {
                let res = ''
                 res = Math.floor(Math.random() * Math.floor(82));
                console.log(res)
                return res;

            },
            getRandomLettre () {
                let items = ['a', 'b', 'c', 'd', 'e','f','j','h','i','g','k','l'];
                let rest = ''
                rest = items[Math.floor(Math.random()*items.length)];
                return rest;
            },
            getResultMovie(){
                this.number = this.getRandomInt()
                const url = `https://hackathon-wild-hackoween.herokuapp.com/movies/${this.number}`;
                let self = this
                this.axios({
                    method: 'get',
                    url: url
                })
                    .then(function (response) {
                        self.movie.img = response.data.movie.posterUrl;
                        self.movie.name = response.data.movie.title
                        self.movie.show = false
                        self.choix = true
                        self.drink.show = true
                        console.log(response.data.movie)
                    }).catch(function (error) {
                }).finally(function () {

                });
            },
            getResultDrink(){

                const url = `https://thecocktaildb.com/api/json/v1/1/search.php?f=${this.lettre}`;
                let self = this
                this.axios({
                    method: 'get',
                    url: url
                })
                    .then(function (response) {
                        self.drink.img = response.data.drinks[0].strDrinkThumb;
                        self.drink.name = response.data.drinks[0].strDrink
                        self.drink.show = false
                        self.choix = true
                       // self.drink.show = true
                        console.log(response.data.drinks[0])
                    }).catch(function (error) {
                }).finally(function () {

                });
            },
            getRandomBouffe(){
                let items = ['a', 'b', 'c', 'd', 'e','f','j','h','i','g','k','l'];
                let nom = ''
                nom = items[Math.floor(Math.random()*items.length)];
                let extension = '.jpg'
                this.bouffe.img = `/images/bouffe/${nom}${extension}`

            }
        }
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
