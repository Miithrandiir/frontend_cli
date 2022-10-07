<template>
  <div>
    <b-form-group>
      <label>Nick name</label>
      <b-form-input v-model="localUser.nick" :class="{'bg-error':!usernameValid}"/>
      <b-form-invalid-feedback :state="usernameValid">
        Ne doit pas être vide
      </b-form-invalid-feedback>
    </b-form-group>
    <b-form-group>
      <label>Fullname</label>
      <b-form-input v-model="localUser.fullname" :class="{'bg-error':!isFullnameValid}"/>
      <b-form-invalid-feedback :state="isFullnameValid">
        Format: "Prénom nom"
      </b-form-invalid-feedback>
    </b-form-group>
    <b-form-group>
      <label>Address</label>
      <b-form-input v-model="localUser.address"/>
    </b-form-group>
    <b-form-group>
      <label>Country</label>
      <b-form-input v-model="localUser.country" disabled/>
    </b-form-group>
    <b-form-group>
      <label>phone number</label>
      <input type="text" class="form-control" :class="{'is-invalid': !isPhonenumberValid}" @input="phoneInput($event)" :value="localUser.phone" maxlength="9"/>
      <b-form-invalid-feedback v-if="!isPhonenumberValid">
        Doit comporter 9 chiffres
      </b-form-invalid-feedback>
    </b-form-group>
  </div>
</template>

<script>
import {User} from '@/assets/js/User';

export default {
  name: "ex_07_UserForm",
  props: {
    user: User
  },
  data() {
    return {
      localUser: this.user
    }
  },
  computed: {
    usernameValid() {
      return this.localUser.nick !== ''
    },
    isFullnameValid() {
      return this.localUser.fullname.split(' ').length === 2;
    },
    isPhonenumberValid() {
      return this.localUser.phone.split('').length === 9;
    }
  },
  methods: {
    phoneInput(event){
      let str = event.target.value.replaceAll(' ', '').trim()
      str = str.replaceAll(/[^0-9]/g, '')
      this.localUser.phone = str
      this.$forceUpdate()
    }
  }
}
</script>

<style scoped>
  .bg-error {
    background: #dc3545;
  }
</style>
