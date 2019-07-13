<template>
        <v-container grid-list-xl>
            <v-layout row wrap>
                
                <v-flex xs6 md6>
                    <v-card class="mb-3" v-for="(item, index) in listaTareas" :key="index">
                    
                        <v-card-text>
                        <v-chip class="ml-0" label color="pink" text-color="white">
                            <v-icon left>label</v-icon>
                           {{item.titulo}}
                        </v-chip>
                        <p>{{item.descripcion}}</p>
                          <v-btn color="warning" @click="editar(index)" class="ml-0">Editar</v-btn>
                          <v-btn color="error" @click="eliminarTarea(item.id)" class="ml-0">Eliminar</v-btn>  
                        </v-card-text>
                    </v-card>

                     <!-- <v-card class="mb-3">
                        <v-card-text>
                        <v-chip class="ml-0" label color="pink" text-color="white">
                            <v-icon left>label</v-icon>
                            Título de tarea #2
                        </v-chip>
                        <p>Mollit velit consequat deserunt est cupidatat dolor dolor. Commodo sint sint 
                            ex occaecat minim nulla pariatur velit. Adipisicing non do pariatur cupidatat 
                            ut sit commodo do. Sunt laboris ex cillum aute enim nisi tempor cillum est.</p>
                          <v-btn color="warning" class="ml-0">Editar</v-btn>
                          <v-btn color="error" class="ml-0">Eliminar</v-btn>  
                        </v-card-text>
                    </v-card>  -->



                </v-flex>
                
                <v-flex xs6 md6 v-if="formAgregar">
                    <v-card class="mb-3 pa-3">
                        <v-card-text>
                        <v-form @submit.prevent="agregarTarea">
                            <v-text-field label="Título de la tarea" v-model="titulo"></v-text-field>
                            <v-textarea label="Descripción de tarea" v-model="descripcion"></v-textarea>
                            <v-btn block color="success" type="submit">Agregar tarea</v-btn>
                        </v-form>
                        </v-card-text>
                    </v-card>
                </v-flex>

                <v-flex xs6 md6 v-if="!formAgregar">
                    <v-card class="mb-3 pa-3">
                        <v-card-text>
                        <v-form @submit.prevent="editarTarea">
                            <v-text-field label="Título de la tarea" v-model="titulo"></v-text-field>
                            <v-textarea label="Descripción de tarea" v-model="descripcion"></v-textarea>
                            <v-btn block color="warning" type="submit">Editar tarea</v-btn>
                        </v-form>
                        </v-card-text>
                    </v-card>
                </v-flex>


            </v-layout>


            <v-snackbar
      v-model="snackbar"
    >
      {{ mensaje }}
      <v-btn
        color="pink"
        flat
        @click="snackbar = false"
      >
        Cerrar
      </v-btn>
    </v-snackbar>

        </v-container>
</template>


<script>
export default {
    data() {
        return {
            listaTareas: [
                {id: 1, titulo: 'Título tarea #1', descripcion: 'Mollit velit consequat deserunt est cupidatat dolor dolor. Commodo sint'
                + 'sint ex occaecat minim nulla pariatur velit. Adipisicing non do pariatur cupidatat ut sit'
                + 'commodo do. Sunt laboris ex cillum aute enim nisi tempor cillum est.' },
                {id: 2, titulo: 'Título tarea #2', descripcion: 'Mollit velit consequat deserunt est cupidatat dolor dolor. Commodo sint'
                + 'sint ex occaecat minim nulla pariatur velit. Adipisicing non do pariatur cupidatat ut sit'
                + 'commodo do. Sunt laboris ex cillum aute enim nisi tempor cillum est.' }
            ],
            titulo: '',
            descripcion: '',
            snackbar: false,
            mensaje: '',
            formAgregar: true,
            indexTarea: ''
        }
    },
    methods: {
     agregarTarea(){
         if (this.titulo == '' || this.descripcion == '') {
             this.snackbar = true
             this.mensaje = 'Los campos están vacíos, debes llenarlos'
         }else{
             this.listaTareas.push({
                 id: Date.now(),
                 titulo: this.titulo,
                 descripcion: this.descripcion
             })
             this.titulo = ''
             this.descripcion = ''
             this.snackbar = true;
             this.mensaje = 'Tarea agregada con éxito'
         }
     },
     eliminarTarea(id){
         this.listaTareas = this.listaTareas.filter(e => e.id != id)
     },
     editar(index){
         this.formAgregar = false
         this.titulo = this.listaTareas[index].titulo
         this.descripcion = this.listaTareas[index].descripcion
         this.indexTarea = index
     },
     editarTarea(){
         this.listaTareas[this.indexTarea].titulo = this.titulo
         this.listaTareas[this.indexTarea].descripcion = this.descripcion
         this.formAgregar = true
         this.titulo = ''
         this.descripcion = ''
         this.snackbar = true
         this.mensaje = 'Tarea editada exitosamente'
     }
    }
}
</script>
