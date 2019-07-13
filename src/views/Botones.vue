<template>
    <v-container>
        <v-layout>
            <v-flex>
                <v-btn>Texto</v-btn>
                <v-btn color="primary">Texto</v-btn>
                <v-btn dark color="blue">Texto</v-btn>

                <v-btn color="warning" large>Largo</v-btn>
                <v-btn color="warning" small>Pequeño</v-btn>

                <v-btn color="warning" large disabled>Largo</v-btn>

                <v-btn color="info" depressed>Botón</v-btn>

                <v-btn color="primary">
                    <v-icon>forum</v-icon>
                </v-btn>

                <v-btn flat icon>
                    <v-icon>forum</v-icon>
                </v-btn>

                <v-btn fab color="primary">
                    <v-icon>forum</v-icon>
                </v-btn>

                <v-btn color="success">Texto
                    <v-icon right>forum</v-icon>
                </v-btn>

                <v-btn round outline color="success">
                    <v-icon left>forum</v-icon>
                    Texto
                </v-btn>

                <v-btn outline block color="success">
                    <v-icon left>forum</v-icon>
                    Texto
                </v-btn>

            </v-flex>
        </v-layout>
    </v-container>
</template>



<script>
export default {
    data() {
        return {
            
        }
    },
}
</script>