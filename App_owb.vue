<template>
  <div id="app">

    (parent->data) globalUser.name : <input class="input-sm" type="text" v-model="globalUser.name"> -> {{ globalUser.name }}

    <hr>

    <fakecard :propUser="globalUser"></fakecard>

  </div>
</template>

<script>
import smpl_04_fakecard_owb_attr from "@/components/smpl_03_fakecard_owb";

export default {
  name: "App",
  components:{
    fakecard: smpl_04_fakecard_owb_attr
  },
  data(){ return {
    globalUser: {
      name: 'Greg'
    }
  }},
}
</script>
