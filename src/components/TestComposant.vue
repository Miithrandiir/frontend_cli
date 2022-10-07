<template>

  <!-- ici démarre le contenu du composant -->
  <div> <!-- NB : il faut un élément 'racine'-->
    {{ message }}
  </div>

</template>

<script>
export default {
  name: "TestComposant", // le nom du composant
  data(){return{
    message: "Je suis un Composant de Test :)"
  }}
}
</script>

<style scoped>

</style>
