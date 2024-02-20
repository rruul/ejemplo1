<template>
  <div>
    <ui-tarjeta
      titulo="Hola a todos"
      subtitulo="texto de prueba"
      texto="texto descriptivo"
      color="red"
      :width="300"
      @btn-aceptar="tarjetaUno"
    />
    <ui-tarjeta
      titulo="Segunda Tarjeta"
      subtitulo="Funcional"
      texto="texto"
      color="primary"
      :width="800"
      :show-cancelar="false"
      @btn-aceptar="tarjetaDos"
    />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    tarjetaUno (data) {
      console.log('presionaste tarjeta uno', data)
    },
    tarjetaDos (data) {
      console.log('presionaste tarjeta dos', data)
    }
  }
}

</script>
