<template>

  <v-container grid-list-md>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <v-card>
          <v-img :src="require('@/assets/syscode.png')"></v-img>
          
          <v-card-title>
            <h3>Aute reprehenderit veniam Lorem proident ad deserunt amet irure.</h3>
          </v-card-title>
          <v-card-text>
            <p>Eiusmod magna ullamco anim non cupidatat amet laborum nostrud enim non magna Lorem.
             Ex reprehenderit aliqua voluptate aliquip dolor officia cillum commodo ea. Dolor consectetur 
             xercitation velit nulla commodo adipisicing laboris sint nostrud enim.</p>
          </v-card-text>
          <v-card-actions>
            <v-btn color="info" flat>Acción</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>

      <v-flex xs12 sm6>
        <v-card>
          <v-img :src="require('@/assets/syscode.png')">
          <v-container>
            <v-layout>
              <v-flex>
                <span class="headline white--text">Incididunt laboris cupidatat.</span>
              </v-flex>
            </v-layout>
          </v-container>
          </v-img>
          <v-card-title>
            <h3>Aute reprehenderit veniam Lorem proident ad deserunt amet irure.</h3>
          </v-card-title>
          <v-card-text>
            <p>Eiusmod magna ullamco anim non cupidatat amet laborum nostrud enim non magna Lorem.
             Ex reprehenderit aliqua voluptate aliquip dolor officia cillum commodo ea. Dolor consectetur 
             xercitation velit nulla commodo adipisicing laboris sint nostrud enim.</p>
          </v-card-text>
          <v-card-actions>
            <v-btn color="info" flat @click="dialog = true">Acción</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>

    <v-layout row wrap>
    <v-flex xs12 sm6>
        <v-card>
          <v-img :src="require('@/assets/syscode.png')">
          <v-container>
            <v-layout>
              <v-flex>
                <span class="headline white--text">Incididunt laboris cupidatat.</span>
              </v-flex>
            </v-layout>
          </v-container>
          </v-img>
          <v-card-title>
            <h3>Aute reprehenderit veniam Lorem proident ad deserunt amet irure.</h3>
          </v-card-title>
          <v-card-text>
            <p>Eiusmod magna ullamco anim non cupidatat amet laborum nostrud enim non magna Lorem.
             Ex reprehenderit aliqua voluptate aliquip dolor officia cillum commodo ea. Dolor consectetur 
             xercitation velit nulla commodo adipisicing laboris sint nostrud enim.</p>
          </v-card-text>
          <v-card-actions>
            <v-btn color="info" flat @click="dialog = true">Acción</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>

  <!--Dialog-->
  <v-dialog v-model="dialog" width="500" persistent>
    <v-card>
      <v-card-title>Este es el título</v-card-title>
      <v-card-text>Ex qui voluptate officia est esse irure et ut est in. 
        Pariatur ad irure commodo voluptate cupidatat dolore quis voluptate dolore ipsum et amet eiusmod. 
        Quis mollit sint mollit exercitation aute incididunt aliquip non proident et Lorem.</v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn @click="dialog = false">Cerrar</v-btn>
        </v-card-actions>
    </v-card>
  </v-dialog>

  <!--Fin Dialog-->

  </v-container>

</template>

<script>
  export default {
   data() {
     return {
       dialog: false
     }
   }
  }
</script>
