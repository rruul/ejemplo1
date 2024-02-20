<template>
  <v-alert
  :color="color"
  :type="type"
  :icon="icon"
  :border="border"
  :dismissible="dismissible"
  >

  </v-alert>
</template>
<script>

export default {
  props: {
  	color: { type: String, default: '' },
    type: { type: String, default: '' },
    icon: { type: String, default: '' },
  	border: { type: String, default: '' },
    dismissible: { type: Boolean, default: false },
    alertText: { type: String, default: '' },
    width: { type: Number,  default: 300 }
  },
}
</script>
<style scoped>
.alerta {
  position: absolute;
  top: 30px;
  right: 10px;
  z-index: 1000;
}
</style>
