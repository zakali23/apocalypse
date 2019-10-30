<template>
    <v-app>
        <!--Navbar-->
        <nav class="navbar navbar-light light-blue lighten-4">

            <!-- Navbar brand -->
            <a class="navbar-brand" href="#">Navbar</a>

            <!-- Collapse button -->
            <button class="navbar-toggler toggler-example" type="button" data-toggle="collapse" data-target="#navbarSupportedContent1"
                    aria-controls="navbarSupportedContent1" aria-expanded="false" aria-label="Toggle navigation"><span class="dark-blue-text"><i
                    class="fas fa-bars fa-1x"></i></span></button>

            <!-- Collapsible content -->
            <div class="collapse navbar-collapse" id="navbarSupportedContent1">

                <!-- Links -->
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item active">
                        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Features</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Pricing</a>
                    </li>
                </ul>
                <!-- Links -->

            </div>
            <!-- Collapsible content -->

        </nav>
        <!--/.Navbar-->
        <v-layout >
            <v-flex md-3 @click="view1" v-if="movie.view1" class="text-sm-center">
                <img :src="movie.img" height="200" width="auto" /><br>
                {{movie.name}}
            </v-flex>
            <v-flex md-3 @click="view2" v-if="movie.view2" class="text-sm-center">
                <img :src="movie.img" height="200" width="auto" />
            </v-flex>
            <v-flex md-3 @click="view3" v-if="movie.view3" class="text-sm-center">
                <img :src="movie.img" height="200" width="auto" />

            </v-flex>
            <v-flex md-3 @click="view4" v-if="movie.view4" class="text-sm-center">
                <img :src="movie.img" height="200" width="auto" />
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
                img:"/images/carte.png/",
                name:''
            }


        }),
        methods: {

            view1 () {

                this.movie.view2 = false
                this.movie.view3 = false
                this.movie.view4 = false
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
            },
            view2 () {

                this.movie.view1 = false
                this.movie.view3 = false
                this.movie.view4 = false
            },
            view3 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view4 = false
            },
            view4 () {

                this.movie.view2 = false
                this.movie.view1 = false
                this.movie.view3 = false
            },
            getRandomInt() {
                let res = ''
                 res = Math.floor(Math.random() * Math.floor(82));
                console.log(res)
                return res;

    }
        }
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
