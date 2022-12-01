<template>
    <div>
        <v-container>
            <v-row>
                <v-col>
                    <h1>POSTS</h1>
                    <br>
                    <div v-for="post in posts">
                        <v-row>
                            <v-col style="background-color: bisque">
                                <v-text-field> placeholder ="Buscar articles ....</v-text-field>   
                            </v-col>
                            <v-col  cols="9" style="background-color: grey">
                                <h4>{{post.title}} ({{post.reactions}} likes)</h4>
                                <nuxt-link 
                                v-bind:to="enllacPost(post.id)">
                                veure post
                            </nuxt-link>
                            </v-col>
                           
                        </v-row>
                    </div>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>
<script>
import posts from '@/dades/posts'
export default{
    mounted() {
        this.posts = posts
    },
    data(){
        return{
            posts:[]

        }

    },
    methods: {
        enllacPost(idPost){
            return "/posts/"+idPost

        }
        
    },
    computed:{
        postsFiltrat(){
            this.postsDeVue.filter((el)=>{
                let titol = el.title
                if(titol.includes(this.textDeCerca)){
                    
                }
            })
        }

    }
}
</script>