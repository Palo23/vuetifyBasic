<template>
  <v-app>
      <v-toolbar app color="cyan">

        <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>

        <v-toolbar-title>
          <v-toolbar-items>
              <img width="150" height="50" :src="require('@/assets/syscode.png')"> </img>
          </v-toolbar-items></v-toolbar-title>
        <v-btn flat to="/"> Inicio </v-btn>
        <v-btn flat to="/about">Acerca</v-btn>
        <v-btn flat to="/botones">Botones</v-btn>
        <v-btn flat to="/tareas">Tareas</v-btn>

        <v-spacer></v-spacer>

        <v-btn flat to="/grid">Grid</v-btn>
      </v-toolbar>

      <v-navigation-drawer app v-model="drawer" temporary dark>
        <v-layout mt-4 column align-center>
          <v-flex>
            <v-avatar>
              <img src="@/assets/icon_syscode.png" alt="">
            </v-avatar>
          </v-flex>
          <v-flex>
            <p class="white--text mt-3 headline">Systems Code</p>
          </v-flex>
        </v-layout>
        <v-layout column>
          <v-flex mx-3>
        <v-btn flat color="teal lighten-1" block to="/"> Inicio </v-btn>
        <v-btn flat color="teal lighten-1" block to="/about">Acerca</v-btn>
        <v-btn flat color="teal lighten-1" block to="/botones">Botones</v-btn>
        <v-btn flat color="teal lighten-1" block to="/tareas">Tareas</v-btn>
          </v-flex>
        </v-layout>
      </v-navigation-drawer>

    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      drawer: false
    }
  }
}
</script>
