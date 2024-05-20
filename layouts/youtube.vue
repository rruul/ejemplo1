<template>
  <v-app id="inspire">
    <v-system-bar app>
      <v-spacer />
      <v-icon>mdi-square</v-icon>
      <v-icon>mdi-circle</v-icon>
      <v-icon>mdi-triangle</v-icon>
    </v-system-bar>
    <ui-alert
      v-if="showAlert"
      :type="type"
      :color="color"
      :border="border"
      :alert-text="text"
      :icon="icon"
    />
    <v-app-bar
      app
      clipped-right
      flat
      height="72"
    >
      <v-spacer />
      <v-responsive max-width="156">
        <v-text-field
          dense
          flat
          hide-controls
          rounded
          solo-inverted
        />
      </v-responsive>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      app
      width="300"
    >
      <v-navigation-drawer
        v-model="drawer"
        absolute
        color="grey lighten-3"
        mini-variant
      >
        <v-avatar
          class="d-block text-center mx-auto mt-4"
          color="grey-darken-1"
          size="36"
        />
        <v-divider class="mx-3 mv-5" />
        <v-avatar
          v-for="n in 6"
          :key="n"
          class="d-block text-center mx-auto mb-9"
          color="grey-lighten-1"
          size="28"
        />
      </v-navigation-drawer>
      <v-sheet
        color="grey-lighten-5"
        height="128"
        width="100%"
      />
      <v-list
        class="pl-14"
        shaped
      >
        <v-list-item
          v-for="n in 5"
          :key="n"
          link
        >
          <v-list-item-content>
            <v-list-item-title>Item {{ n }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-navigation-drawer
      app
      cliped
      right
    >
      <v-list>
        <v-list-item
          v-for="n in 5"
          :key="n"
          link
        >
          <v-list-item-content>
            <v-list-item-title>Item {{ n }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <Nuxt />
    </v-main>
    <v-footer
      app
      color="trasnparent"
      height="72"
      inset
    >
      <v-text-field
        bg-color="grey-lighten-1"
        dense
        flat
        hide-details
        rounded
        solo
      />
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: null,
      showAlert: false,
      type: '',
      color: '',
      border: '',
      text: '',
      icon: ''
    }
  },
  created () {
    this.$nuxt.$on('show-alert', $event => this.cambiaDatos($event))
  },
  methods: {
    cambiaDatos (datos) {
      console.log('@@ ->', datos)
      this.color = datos.color
      this.type = datos.type
      this.text = datos.text
      this.border = datos.border
      this.width = datos.width
      this.icon = datos.icon
      this.showAlert = true
      setTimeout(() => {
        this.showAlert = false
      }, datos.time)
    }
  }
}
</script>
