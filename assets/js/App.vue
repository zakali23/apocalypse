<template>
    <v-app>
&nbsp:<br/>
        <h1 class="text-sm-center">Avec quel monstre passerez-vous Halloween ?</h1>
        <template v-if="bouffe.show">
            <h2 class="text-sm-center">Quel plat pour votre Halloween ?</h2>
            <v-layout >
                <v-flex md-3 @click="view13" v-if="bouffe.view1" class="text-sm-center cartePlat">
                    <img src="/images/carte.png/" :height="ht" width="auto" /><br>
                </v-flex>
                <v-flex md-3 @click="view14" v-if="bouffe.view2" class="text-sm-center cartePlat">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click="view15" v-if="bouffe.view3" class="text-sm-center cartePlat">
                    <img src="/images/carte.png/" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click="view16" v-if="bouffe.view4" class="text-sm-center cartePlat">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click="view17" v-if="bouffe.view5" class="text-sm-center cartePlat">
                    <img src="/images/carte.png/" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click="view18" v-if="bouffe.view6" class="text-sm-center cartePlat">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
            </v-layout>
        </template>
        <template v-if="drink.show">
            <h2  class="text-sm-center">Une boisson ?</h2>
            <v-layout >
                <v-flex md-3 @click="view7" v-if="drink.view1" class="text-sm-center carteCocktail">
                    <img src="/images/carte.png/" :height="ht" width="auto" /><br>
                </v-flex>
                <v-flex md-3 @click="view8" v-if="drink.view2" class="text-sm-center carteCocktail">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click="view9" v-if="drink.view3" class="text-sm-center carteCocktail">
                    <img src="/images/carte.png/" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click="view10" v-if="drink.view4" class="text-sm-center carteCocktail">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click="view11" v-if="drink.view5" class="text-sm-center carteCocktail">
                    <img src="/images/carte.png/" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click="view12" v-if="drink.view6" class="text-sm-center carteCocktail">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
            </v-layout>
        </template>
        <template v-if="filler.show">
                <v-flex md-3  v-if="filler.view" class="text-sm-center">
                    <img src="/images/carte.png/" height="280px" width="auto" style="opacity: 0;"/><br>
                </v-flex>

        </template>
        <template v-if="movie.show">
            <h2  class="text-sm-center">Et un film, pour vous détendre</h2><br>
            <v-layout v-if="movie.show">
                <v-flex md-3 @click="view1" v-if="movie.view1" class="text-sm-center carteMovie">
                    <img src="/images/carte.png/" :height="ht" width="auto" /><br>
                </v-flex>
                <v-flex md-3 @click="view2" v-if="movie.view2" class="text-sm-center carteMovie">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click="view3" v-if="movie.view3" class="text-sm-center carteMovie">
                    <img src="/images/carte.png/" :height="ht" width="auto" />

                </v-flex>
                <v-flex md-3 @click="view4" v-if="movie.view4" class="text-sm-center carteMovie">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click="view5" v-if="movie.view5" class="text-sm-center carteMovie">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
                <v-flex md-3 @click="view6" v-if="movie.view6" class="text-sm-center carteMovie">
                    <img src="/images/carte.png/" :height="ht" width="auto" />
                </v-flex>
            </v-layout>
        </template>
        <template v-if="choix">
            <v-layout >
                <v-flex md4  v-if="res1" class="text-sm-center bordure">
                    <img :src="bouffe.img" :height="choixht" width="auto"  style="border : 5px solid white !important;"/><br>
                   <span> {{bouffe.name}}</span>
                </v-flex>
                <v-flex md4  v-if="res2" class="text-sm-center bordure">
                    <img :src="drink.img" :height="choixht" width="auto"  style="border : 5px solid white !important;"/><br>
                    <span> {{drink.name}}</span>
                </v-flex>
                <v-flex md4  v-if="res3" class="text-sm-center bordure">
                    <img :src="movie.img" :height="choixht" width="auto" style="border : 5px solid white !important;"/><br>
                    <span>{{movie.name}}</span>
                </v-flex>


            </v-layout>
        </template>

        <template v-if="monster.show">
            <div class="resultFond">
            <div class="result">
            <div class="resultTitle">
<!--            <h1 class="text-sm-center">Vous avez l'honneur d'être : </h1> -->
            <h1 class="text-sm-center">{{monster.name}}</h1>
            </div>
            <div class="resultFiche">
            <v-layout >
                <v-flex md-6 v-if="monster" class="text-sm-center carteMonster" style="display:flex; justify-content:center;">
                <table width="490px" height="320px">
                    <tr>
                        <td rowspan="8"><img :src="monster.img" :height="ht" width="auto" class="monsterPic"/></td>
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
            </div>
            </div>
            <div class="restart" style="position:absolute;right:50px;bottom:50px;color=#EEEEEE;background-color:#FFF;padding:0px 0px 0px 5px ; border-radius:5px;"><a class="mescouilles" href="" onclick="window.location.reload();">Try again <img src="/images/restart.png" height="50px" ></a></div>
            </div>

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
            filler:{
                show:false,
                view:true,
                img:"/images/waitingCard.png/",

            },
            movie:{
                show:false,
                view1:true,
                view2:true,
                view3:true,
                view4:true,
                view5:true,
                view6:true,
                img:"/images/waitingCard.png/",
                name:'',
                id:'0',
            },
            drink:{
                show:false,
                view1:true,
                view2:true,
                view3:true,
                view4:true,
                view5:true,
                view6:true,
                img:"/images/waitingCard.png/",
                name:''
            },
            bouffe:{
                show:true,
                view1:true,
                view2:true,
                view3:true,
                view4:true,
                view5:true,
                view6:true,
                img:"/images/waitingCard.png/",
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
            choix:true


        }),
        methods: {
           view1 () {

                this.filler.view = true
                this.filler.show = true

                this.number = this.getRandomInt()
                this.getResultMovie()

                this.movie.view2 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
             },
            view2 () {

                this.filler.view = true
                this.filler.show = true

                this.getResultMovie()
                this.movie.view1 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
 
            },
            view3 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.filler.show = true
                this.filler.view = true
//                this.res3 = true
                this.getResultMovie()
            },
            view4 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.movie.view3 = false
                this.filler.show = true
                this.filler.view = true
//                this.res3 = true
                this.getResultMovie()
            },
            view5 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view4 = false
                this.movie.view6 = false
                this.movie.view3 = false
                this.filler.show = true
                this.filler.view = true
//                this.res3 = true
                this.getResultMovie()
            },
            view6 () {
//                this.res3 = true

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view5 = false
                this.movie.view4 = false
                this.movie.view3 = false
                this.filler.show = true
                this.filler.view = true
                this.res1 = true
                this.getResultMovie()
            },

            view7 () {

                this.lettre = this.getRandomLettre()
                this.getResultDrink()
                this.drink.view2 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view6 = false
            },
            view8 () {
//                this.res2 = true
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
                this.drink.view1 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view6 = false

            },
            view9 () {
//                this.res2 = true
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
                this.drink.view2 = false
                this.drink.view1 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view6 = false
            },
            view10 () {
 //               this.res2 = true
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
                this.drink.view2 = false
                this.drink.view3 = false
                this.drink.view1 = false
                this.drink.view5 = false
                this.drink.view6 = false
            },
            view11 () {
//                this.res2 = true
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
                this.drink.view2 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view1 = false
                this.drink.view6 = false
            },
            view12 () {
//                this.res2 = true
                this.lettre = this.getRandomLettre()
                this.getResultDrink()
                this.drink.view1 = false
                this.drink.view3 = false
                this.drink.view4 = false
                this.drink.view5 = false
                this.drink.view2 = false
            },
            view13 () {
//                this.res1 = true
                this.bouffe.view1 = false
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
            },
            view14 () {
//                this.res1 = true
                this.bouffe.view1 = false
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
            },
            view15 () {
//                this.res1 = true
                this.bouffe.view2 = false
                this.bouffe.view1 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
            },
            view16 () {
//                this.res1 = true
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view1 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()

            },
            view17 () {
//                this.res1 = true
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view1 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.getRandomBouffe()
            },
            view18 () {
//                this.res1 = true
                this.bouffe.view2 = false
                this.bouffe.view3 = false
                this.bouffe.view4 = false
                this.bouffe.view5 = false
                this.bouffe.view6 = false
                this.bouffe.view1 = false
                this.getRandomBouffe()
            },
            verifieDrink(machin,i) {
                for (i=1;i<7;i++){
                let el = machin+'.view' +i;
//                alert(el)
                    if (i==num){
                        this.el = true;
                    } 
                    else {
                        this.el = false;
                    } 
                }
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
                        self.movie.name = (response.data.movie.title).replace(/_/g,' ')
                        self.movie.id = response.data.movie.id
                        console.log("id movie : "+self.movie.id)
                        self.movie.show = false
                        self.choix = true
                        self.drink.show = false
                       // console.log(response.data.movie)
                    }).catch(function (error) {
                }).finally(function () {

                });
//                alert('pouet')
                this.res3 = true

                 this.getResultMonster()

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
                        self.choix = true
                        self.drink.show = false
                        self.movie.show = true
                       // console.log(response.data.drinks[0])
                    }).catch(function (error) {
                }).finally(function (response) {

                });
                this.res2 = true
            },

            getRandomBouffe(){
                //alert('putain !!')
              let items = ['caviar_sanguinolant', 'céleris', 'choucroute', 'entrecote_de_zombie', 'hamburger_dechu','kebap_de_la_mort','lasagnes_de_ta_grand_mere','pizza_input','schneck_en_croute','steak_saignant','sushi_au_mercure','tacos_gluant'];
              let nom = '';
              this.numRandom = Math.floor(Math.random()*items.length)
              nom = items[this.numRandom];
              this.bouffe.name = (nom).replace(/_/g,' ')
//              this.bouffe.name = nom;
              let extension ='.jpg';
              this.bouffe.img = `/images/bouffe/${nom}${extension}`

                this.res1 = true
                this.bouffe.show = false
                this.drink.show = true

            },

            getResultMonster(){
                let pouet = (this.movie.id + this.drink.id + this.numRandom)%20 +1
                console.log(this.movie.id)
                console.log(this.drink.id)
                console.log(this.numRandom)
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
                    this.res3 = true
                    
                });
            },
        }
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
