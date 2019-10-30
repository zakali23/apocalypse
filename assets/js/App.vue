<template>
    <v-app>

        <h1  class="text-sm-center">Les Films secrets</h1>
        <v-layout >
            <v-flex md-3 @click.once="view1" v-if="movie.view1" class="text-sm-center">
                <img :src="movie.img" height="280" width="auto" /><br>
            </v-flex>
            <v-flex md-3 @click="view2" v-if="movie.view2" class="text-sm-center">
                <img :src="movie.img" height="280" width="auto" />
            </v-flex>
            <v-flex md-3 @click="view3" v-if="movie.view3" class="text-sm-center">
                <img :src="movie.img" height="280" width="auto" />
            </v-flex>
            <v-flex md-3 @click="view4" v-if="movie.view4" class="text-sm-center">
                <img :src="movie.img" height="280" width="auto" />
            </v-flex>
            <v-flex md-3 @click="view5" v-if="movie.view5" class="text-sm-center">
                <img :src="movie.img" height="280" width="auto" />
            </v-flex>
            <v-flex md-3 @click="view6" v-if="movie.view6" class="text-sm-center">
                <img :src="movie.img" height="280" width="auto" />
            </v-flex>
        </v-layout>

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
            name:'',
            nameErrors:'',
            number:'',
            movies:[],
            rotation:'cont',
            movie:{
                view1:true,
                view2:true,
                view3:true,
                view4:true,
                view5:true,
                view6:true,
                img:"/images/carte.png/",
                name:''
            }


        }),
        methods: {

            view1 () {
            if (this.movie.view2 == true) {

                this.movie.view2 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
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
                       console.log(response.data.movie)
                   }).catch(function (error) {
               }).finally(function () {

               });
               }
            },
            view2 () {
            if (this.movie.view1 == true) {
                this.movie.view1 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.getResultMovie()
                }
            },
            view3 () {
            if (this.movie.view1 == true) {
                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.getResultMovie()
                }
            },
            view4 () {
              if (this.movie.view1 == true) {
                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view3 = false
                this.movie.view5 = false
                this.movie.view6 = false
                this.getResultMovie()
                }
            },
            view5 () {
            if (this.movie.view1 == true) {
                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view6 = false
                this.getResultMovie()
                }
            },
            view6 () {
            if (this.movie.view1 == true) {
                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view3 = false
                this.movie.view4 = false
                this.movie.view5 = false
                this.getResultMovie()
                }
            },
            getRandomInt() {
                let res = ''
                 res = Math.floor(Math.random() * Math.floor(82));
                console.log(res)
                return res;

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
                        console.log(response.data.movie)
                    }).catch(function (error) {
                }).finally(function () {

                });
            }
        }
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
