<template>
    <v-app id="inspire">
      <v-system-bar>
        <v-spacer />
        <v-icon>mdi-square</v-icon>
        <v-icon>mdi-circle</v-icon>
        <v-icon>mdi-triangle</v-icon>
      </v-system-bar>
      
  
      <v-navigation-drawer
        color="grey-lighten-3"
        rail
      >
        <v-avatar
          class="d-block text-center mx-auto mt-4"
          color="grey-darken-1"
          size="36"
        ></v-avatar>
  
        <v-divider class="mx-3 my-5"></v-divider>
  
        <v-avatar
          v-for="n in 6"
          :key="n"
          class="d-block text-center mx-auto mb-9"
          color="grey-lighten-1"
          size="28"
        ></v-avatar>
      </v-navigation-drawer>
  
      <v-navigation-drawer width="244">
        <v-sheet
          color="grey-lighten-5"
          height="128"
          width="100%"
        ></v-sheet>
  
        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            :title="`Item ${ n }`"
            link
          ></v-list-item>
        </v-list>
      </v-navigation-drawer>
  
      <v-app-bar
        class="px-3"
        color="grey-lighten-4"
        flat
        height="72"
      >
        <v-spacer></v-spacer>
  
        <v-responsive max-width="156">
          <v-text-field
            bg-color="grey-lighten-1"
            density="compact"
            flat
            hide-details
            rounded="pill"
            variant="solo-filled"
          ></v-text-field>
        </v-responsive>
      </v-app-bar>
  
      <v-main>
        <ui-alert
        v-if="showAlert"
        :type="success"
        :color="green darkeen-4"
        :border="top"
        :alert-text="Alerta Inicial"
        :icon="mdi-account"
        />
        <Nuxt />
      </v-main>
  
      <v-navigation-drawer location="right">
        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            :title="`Item ${ n }`"
            link
          ></v-list-item>
        </v-list>
      </v-navigation-drawer>
  
      <v-footer
        app
        height="72"
      >
        <v-text-field
          bg-color="grey-lighten-1"
          class="overflow-hidden"
          density="compact"
          flat
          hide-details
          rounded="pill"
          variant="solo-filled"
        ></v-text-field>
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
        this.color = datos.coleor
        this.type = datos.type
        this.text = datos.text
        this.border = datos.border
        this.width = datos.width
        this.icon = datos.icon
        this.showAlert = true
        setTimeout(()=>{
          this.showAlert = false
        }, datos.time)
      }
    }
  }
</script>