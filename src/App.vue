<template>
  <div id="app">
    <h1 class="text-center">User information</h1>

    <div class="d-flex flex-row w-75 align-items-center justify-content-between m-auto">

      <Ex_07_UserForm :user="user"/>

      <ex_06_UserCard :user="user"/>
    </div>

    <hr/>

    <div class="d-flex align-items-center flex-column justify-content-center">
      <Ex_08_Country v-for="(value) in countries" :key="value.name" :country="value"></Ex_08_Country>
    </div>
  </div>
</template>

<script>
import ex_06_UserCard from "@/components/ex_06_UserCard";
import {User} from "@/assets/js/User";
import {countries} from "@/assets/js/sample_countries";
import Ex_07_UserForm from "@/components/ex_07_UserForm";
import Ex_08_Country from "@/components/ex_08_Country";

export default {
  name: 'App',
  data() {
    return {
      user: new User({
        nick: 'Arthas',
        fullname: 'Arthas Menethil',
        address: 'Frozen Throne',
        country: 'France',
        phone: '643703007'
      }),
      countries
    }
  },
  components: {
    Ex_08_Country,
    Ex_07_UserForm,
    ex_06_UserCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
