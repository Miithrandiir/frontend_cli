<template>
  <div>

    <!-- ici la balise d'un composant Bootstrap Vue -->
    <b-form-input v-model="message" placeholder="Entrez un message"></b-form-input>

    <div class="mt-2">

      <!-- ici la balise d'un composant Bootstrap Vue Icon -->
      <b-icon icon="exclamation-triangle"></b-icon>

      : {{ message }}

    </div>


  </div>

</template>

<script>
import Vue from 'vue'
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

// Install BootstrapVue
Vue.use(BootstrapVue)
// Optionally install the BootstrapVue icon components plugin
Vue.use(IconsPlugin)

export default {
  name: "TestBootstrapVue", // le nom du composant
  data(){return{
    message: "Je suis un Composant de Test"
  }}
}
</script>
