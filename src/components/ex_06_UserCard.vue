<template>


  <b-card>
    <b-card-body>

      <div class="d-flex flex-row justify-content-between">
        <img :src="userFace" alt="" width="48" height="48"/>
        <div class="d-flex flex-column" style="text-align: right;">
          <h1>{{ user.nick }}</h1>
          <h2>{{ user.fullname }}</h2>
        </div>
      </div>

      <div class="d-flex text-center flex-column">
        <p>{{ user.address }}</p>
        <p>{{ user.country }}</p>
        <p>{{ tel_formated }}</p>
      </div>

    </b-card-body>
  </b-card>

</template>

<script>
import userFace from '@/assets/user_face.png';
import {User} from '@/assets/js/User';
import {countries} from "@/assets/js/sample_countries";

export default {
  name: "ex_06_UserCard",
  data() {
    return {
      userFace: userFace,
    }
  },
  props: {
    user: User
  },
  computed: {
    tel_formated() {
      let search = countries.find(x => x.name === this.user.country);
      let res = "(+" + search.callingCodes[0] + ") ";
      if ( this.tel !== '' ) {
        res += this.user.phone.substring(0, 1);
        if ( this.user.phone.substring(1) !== '' ) {
          let myData = this.user.phone.substring(1).match(/.{1,2}/g);
          res += " " + myData.join(' ');
        }
      }
      return res;
    },
  }
}
</script>

<style scoped>

</style>
