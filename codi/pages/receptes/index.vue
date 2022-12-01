<template>
    <v-container>
        <v-row>
            <v-col>
                <h1>Receptes</h1>

                <div v-for="recepta in receptes">
                    <v-row>
                        <v-col cos="2">
                            <v-img :src="recepta.strDrinkThumb"
                            height="60px"
                            width="60px"></v-img>
                        </v-col>
                        <v-col>
                            <h1>{{recepta.strDrink}}</h1>
                            <h3 style="font-weght:100">{{recepta.strCategory}}</h3>
                            <nuxt-link 
                                v-bind:to="enllacRecepta(recepta.idDrink)">
                                veure recepta
                            </nuxt-link>
                            <br>
                            <nuxt-link :to="'/receptes/'+ recepta.idDrink">enllaç2</nuxt-link>
                        </v-col>
                    </v-row>
                   
                </div>
                <pre>
                    {{receptes}}
                </pre>
                
            </v-col>
        </v-row>
    </v-container>
</template>
<script>
//carregem les dades
import {receptes} from '@/dades/receptes'
export default{
    mounted(){
        //quan el component s'assignat assignem les receptes
        this.receptes =receptes

    },
    data(){
        return{
            receptes:[]
        }
    },
    methods: {
        enllacRecepta(idDeRecepta){
            return "/receptes/"+idDeRecepta

        }
        
    },

}
</script>