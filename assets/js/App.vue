<template>
    <v-app>
        <br><br>
        <h1 class="text-sm-center">Quel est votre monstre totem ?</h1>
        <template v-if="choix">
            <h2  class="text-sm-center text--white">Mes choix :</h2><br>
            <v-layout >
                <v-flex md4  v-if="res1" class="text-sm-center bordure">
                    <img :src="movie.img" :height="choixht" width="auto" style="border : 5px solid white !important;"/><br>
                    <span>{{movie.name}}</span>
                </v-flex>

                <v-flex md4  v-if="res2" class="text-sm-center bordure">
                    <img :src="drink.img" :height="choixht" width="auto"  style="border : 5px solid white !important;"/><br>
                    <span> {{drink.name}}</span>
                </v-flex>

                <v-flex md4  v-if="res3" class="text-sm-center bordure">
                    <img :src="bouffe.img" :height="choixht" width="auto"  style="border : 5px solid white !important;"/><br>
                   <span> {{bouffe.name}}</span>
                </v-flex>

            </v-layout>
        </template>
        <template v-if="movie.show">
            <h2  class="text-sm-center">Les Films secrets</h2><br>
            <v-layout v-if="movie.show">
                <v-flex md-3 @click.once="view1" v-if="movie.view1" class="text-sm-center">
                    <img :src="movie.img" :height="ht" width="auto" /><br>
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
            <h2  class="text-sm-center">Les boissons en sang</h2>
            <v-layout >
                <v-flex md-3 @click.once="view7" v-if="drink.view1" class="text-sm-center carteCocktail">
                    <img :src="drink.img" :height="ht" width="auto" /><br>
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
        <template v-if="bouffe.show">
            <h2 class="text-sm-center">Les boissons en sang</h2>
            <v-layout >
                <v-flex md-3 @click="view13" v-if="bouffe.view1" class="text-sm-center cartePlat">
                    <img :src="bouffe.img" :height="ht" width="auto" /><br>
                </v-flex>
                <v-flex md-3 @click.once="view14" v-if="bouffe.view2" class="text-sm-center cartePlat">
                    <img :src="bouffe.img" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click.once="view15" v-if="bouffe.view3" class="text-sm-center cartePlat">
                    <img :src="bouffe.img" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click.once="view16" v-if="bouffe.view4" class="text-sm-center cartePlat">
                    <img :src="bouffe.img" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click.once="view17" v-if="bouffe.view5" class="text-sm-center cartePlat">
                    <img :src="bouffe.img" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click.once="view18" v-if="bouffe.view6" class="text-sm-center cartePlat">
                    <img :src="bouffe.img" :height="ht" width="auto" />
                </v-flex>
            </v-layout>
        </template>
        <template v-if="monster.show">
        <h1 class="text-sm-center">Vous avez l'honneur d'être : </h1>
        <v-layout >
            <v-flex md-6 v-if="monster" class="text-sm-center carteMonster" style="display: flex; justify-content: center; align-items: center;background-image: url('/images/parchemin.png'); width: 510px;margin: 0 auto">
            <table border="3" width="490px" height="320px">
                <tr>
                    <td rowspan="8"><img :src="monster.img" :height="ht" width="auto" /></td>
                    <td colspan="2">Level</td>
                </tr>
                <tr>
                    <td colspan="2">{{monster.lvl}}</td>
                </tr>
                <tr>
                    <td>Attack</td>
                    <td>Defense</td>
                </tr>
                <tr>
                    <td>{{monster.atck}}</td>
                    <td>{{monster.def}}</td>
                </tr>
                <tr>
                    <td colspan="2">Special</td>
                </tr>
                <tr>
                    <td colspan="2">{{monster.spec}}</td>
                </tr>
                <tr>
                    <td colspan="2">Description</td>
                </tr>
                <tr>
                    <td colspan="2">{{monster.desc}}</td>
                </tr>
            </table>
            </v-flex>
        </v-layout>
    </template>




    </v-app>

</template>

<script>
    import axios from 'axios';
    import 'vuetify/dist/vuetify.min.css';
    import '@mdi/font/css/materialdesignicons.css';
    import search from './components/search.vue';
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
            numRandom:0,
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
            monster:{
                show:false,
                img:'',
                lvl:'',
                atck:'',
                def:'',
                spec:'',
                desc:'',
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
            view13 () {
                this.res3 = true
                this.bouffe.view1 = false
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
              this.getResultMonster()
            },
            view14 () {
                this.res3 = true
                this.bouffe.view1 = false
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
            //    this.getResultBouffe()
              this.getResultMonster()
            },
            view15 () {
                this.res3 = true
                this.bouffe.view2 = false
                this.bouffe.view1 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
            //    this.getResultBouffe()
              this.getResultMonster()
            },
            view16 () {
                this.res3 = true
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view1 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
            //    this.getResultBouffe()
                              this.getResultMonster()

            },
            view17 () {
                this.res3 = true
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view1 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
              //  this.getResultBouffe()
              this.getResultMonster()
            },
            view18 () {
                this.res3 = true
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.bouffe.view1 = false
                this.getRandomBouffe()
              //  this.getResultBouffe()
              this.getResultMonster()
            },
            getRandomInt() {
                let res = ''
                 res = Math.floor(Math.random() * Math.floor(82));
               // console.log(res)
                return res;

            },
            getRandomLettre () {
                let items = ['a', 'b', 'c', 'd', 'e','f','j','h','i','g','k','l','m','n','o','p','q','r','s','t','u','v'];
                return items[Math.floor(Math.random()*items.length)];
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
                        self.movie.name = (response.data.movie.title).replace('_',' ')
                        self.movie.id = response.data.movie.id
                        self.movie.show = false
                        self.choix = true
                        self.drink.show = true
                       // console.log(response.data.movie)
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
                        self.drink.id = response.data.drinks[0].idDrink
                        self.drink.show = false
                        self.bouffe.show = true
                        self.choix = true
                       // self.drink.show = true
                       // console.log(response.data.drinks[0])
                    }).catch(function (error) {
                }).finally(function () {

                });
            },

            getRandomBouffe(){
            	//alert('putain !!')
              let items = ['caviar_sanguinolant', 'céleris', 'choucroute', 'entrecote_de_zombie', 'hamburger_dechu','kebap_de_la_mort','lasagnes_de_ta_grand_mere','pizza_input','schneck_en_croute','steak_saignant','sushi_au_mercure','tacos_gluant'];
              let nom = '';
              this.numRandom = Math.floor(Math.random()*items.length)
              nom = items[this.numRandom];
              this.bouffe.name = nom;
              let extension ='.jpg';
              this.bouffe.img = `/images/bouffe/${nom}${extension}`
                this.bouffe.show = false
            },

            getResultMonster(){
                let pouet = (this.movie.id + this.drink.id + this.numRandom)%20
                console.log(pouet)

	            const url = `https://hackathon-wild-hackoween.herokuapp.com/monsters/${pouet}`;
                let self = this
                console.log(url)
                this.axios({
                    method: 'get',
                    url: url
                })
                    .then(function (response) {
                        self.monster.img = response.data.monster.picture;
                        self.monster.name = response.data.monster.name
                        self.monster.id = response.data.monster.id
                        self.monster.atck = response.data.monster.attack
                        self.monster.def = response.data.monster.defense
                        self.monster.desc = response.data.monster.description
                        self.monster.lvl = response.data.monster.level
                        self.monster.spec = response.data.monster.special
                        self.monster.show = true
                        self.choix = true
                    }).catch(function (error) {
			        }).finally(function () {
                });
                this.monster.show = true
        	},
        }
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
