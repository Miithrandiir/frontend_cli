<template>
  <div>
    <label>(fils->props) propUser.name</label> :
    <input class="input-sm" type="text" v-model="propUser.name">
    {{ propUser.name }}

    <br>

    <label>(fils->data) localUser.name</label> :
    <input class="input-sm" type="text" v-model="localUser.name">
    {{ localUser.name }}
  </div>
</template>

<script>
export default {
  name: "smpl_04_fakecard_owb_attr",
  props:{ // <------------ déclaration des paramètres ---------------------------
    propUser: Object, // le type n'est pas obligatoire, mais c'est mieux de le mettre
  },
  data(){return {
    localUser: this.propUser
  }}
}
</script>

<style scoped>
.mdl-card{
  min-height: 70px ;
}
</style>
