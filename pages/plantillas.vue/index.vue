<template>
    <v-row>
        <v-btn class="ma-2 pa-2" color="green" block @click="muestraAlerta">
            Muestra Alerta
        </v-btn>
        <ui-tarjeta
        v-for="(card, index) in objetos"
        :keys="index"
        :titulo="card.titulo"
        :texto="card.texto"
        :color="card.color"
        :width="400"
        class="ma-2"
        />
    </v-row>

</template>

<script>
export default {
    layout: 'youtube',
    data () {
        return {
            objetos: [
                {titulo: 'uno', texto: 'texto uno', color: 'red'},
                {titulo: 'dos', texto: 'texto dos', color: 'blue'},
                {titulo: 'tres', texto: 'texto tres', color: 'green'},
                {titulo: 'cuatro', texto: 'texto cuatro', color: 'yellow'},
                {titulo: 'cinco', texto: 'texto cinco', color: 'purple'}
            ]
        }
    },
    methods: {
        muestraAlerta () {
            this.$nuxt.$emit('show-alert', {
            color: 'blue darkeen-2',
            type: 'warning',
            text: 'Alerta desde un elemnto hijo',
            icon: 'mdi-account',
            border: 'bottom',
            width: 600,
            time: 5000
        })
        }
    }
}
</script>