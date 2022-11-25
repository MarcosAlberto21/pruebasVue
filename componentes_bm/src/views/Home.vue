<template>
  <v-app>
    <v-main>
    <div class="home">
      <img alt="Vue logo" src="../assets/logo.png">
      <HelloWorld msg="Welcome to Your Vue.js App"/>
      <customTable :columns="columnas" :rows="filas" :icon_edit="'edit'" :titleTable="'Titulo de la tabla'" :item="item"></customTable>
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
    HelloWorld,customTable
  },

  data() {
    return {

      loading: false,
      columnas: 
      [
        {text: "descripcion" , value:"descripcion"},
        {text: "acciones" ,value:"actions"}
      ],

      filas: [
        {id:1,descripcion:"item 1"},
        {id:2,descripcion:"item 2"},
        {id:3,descripcion:"item 3"},
      ],

      item:{
        descripcion: "",
      }

    };
  },
}
</script>
