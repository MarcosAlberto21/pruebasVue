<template>
  <v-app>
    <v-main>
      <div class="home">
        <img alt="Vue logo" src="../assets/logo.png">
        <HelloWorld msg="Welcome to Your Vue.js App" />
        <v-card>
          <v-data-table :headers="columnas_t" :items="filas_t" :search="search">
            <template v-slot:top>
              <customTable @find="find" :size_letter_title="30" :size_letter_data="10" :search="search" :columns="columnas_pdf" :rows="filas_t" :titleTable="'Titulo de la tabla'"></customTable>
            </template>

          </v-data-table>
        </v-card>
      </div>
    </v-main>
  </v-app>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

import { customTable } from "vuetify-more-component";
export default {
  name: 'Home',
  components: {
    HelloWorld, customTable
  },

  data() {
    return {

      loading: false,
      columnas_t:
        [     
        {  text: "id", value: "id", align:"center"},
        { text: "descripcion", value: "descripcion", align:"center" },

        ],

      filas_t: [
        { id: 1, descripcion: "item 1" },
        { id: 2, descripcion: "item 2" },
        { id: 3, descripcion: "item 3" },
        { id: 4, descripcion: "ITEM 3" },
        { id: 5, descripcion: "ÍTEM 3" },
        { id: 6, descripcion: "ÍTEM" },
        { id: 7, descripcion: "ÍTEM3" },
      ],

      columnas_pdf:
        [     
        "ID","DESCRIPCION"
        ],

      search: "",

    };
    
  },

  methods:{
    find(data){
      this.search = data;
    }
  }
}
</script>
