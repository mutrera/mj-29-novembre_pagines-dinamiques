<template>
    <v-container>
        <v-row>
            <v-col cosl="12" md="6">
                <h1>{{receptaVue.strDrink}}</h1>

            </v-col>
            <v-col cosl="12" md="6">
              <pre>
                {{receptaVue}}
              </pre>
            </v-col>
        </v-row>
    </v-container>

</template>
<script>
import {receptes} from '@/dades/receptes.js'
export default{
    mounted(){
        let idDrink=this.$route.params.recepta
        var self = this
        //var self =this, aixo es fa perque a vegades el this no es un component de vue es altra cosa pertanyent al if
        receptes.forEach(recepta => {      
            if(idDrink == recepta.idDrink){
            //Hem trobat la recepta
            self.receptaVue = recepta
            // sef.recepta = recepta
            }
        })



    },
    data(){
        return{
            receptaVue:{}
        }
    }
}
</script>