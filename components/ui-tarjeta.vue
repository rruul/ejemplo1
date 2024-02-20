<template>
	<v-card :color="color" :width="width">
  	<v-card-title>{{ titulo }}</v-card-title>
  	<v-card-subtitle>{{ subtitulo }}</v-card-subtitle>
    <v-card-text>{{ texto }}</v-card-text>
    <v-card-actions>
    	<v-row align="center" justify="center" class="ma-2">
        <v-btn v-if="showCancelar">
          Cancelar
        </v-btn>
        <v-btn @click="emitirEvento">
          Aceptar
        </v-btn>
      </v-row>
    </v-card-actions>
  </v-card>
</template>

<script>
  export default {
    props: {
      titulo: { type: String, default: '' },
      subtitulo: { type: String, default: '' },
      texto: { type: String, default: '' },
      color: { type: String, default: '' },
      width: { type: Number, default: 500 },
      showCancelar: { type: Boolean, default: true }
    },
    methods: {
      emitirEvento () {
        this.$emit('btn-aceptar', {
          date: Date.now(),
          otro: 700
        })
      }
    }
  }
</script>
