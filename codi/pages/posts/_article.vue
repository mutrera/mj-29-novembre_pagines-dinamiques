<template>
    <v-container>
        <v-row v-if="post">
            <v-col cols="12" md="6">
                <h1>{{post.title}}</h1>
                <p>{{post.body}}</p>
            </v-col>
            <v-col cols="12" md="6">
                <pre>
                <nuxt-link to="/posts">Inici</nuxt-link>
                </pre>
            </v-col>
        </v-row>
        <v-row v-else>
            <v-col>
                <h2> No he trobat l'article amv ide{{$route.params.article}} que busques, ves a l'<nuxt-link to="/">inici</nuxt-link> o mira altres <nuxt-link to="/posts">articles</nuxt-link></h2>
            </v-col>
        </v-row>
    </v-container>
</template>
<script>
import posts from '@/dades/posts.js'
export default{
    mounted() {
      let id = this.$route.params.article
        //la funcio find fa el mateix que la foreachs pero la primera para quan la troba
         let post = posts.find((el)=>{
            if(id == el.id){
                return true
            }
        })
        this.post = post
        },
    
    data(){
        return{
            post:[]

        }
    }
}
</script>