<template>
  <div>
    <div class="input">
      <input type="text" v-model="username" name="name" id="name" aria-label="" placeholder="Entrez votre nom">
    </div>

    <div class="card">
      <div class="body">
        <b id="username" v-if="username !== ''">{{ username }}</b>
        <div class="info">
          <p id="nickname" v-if="username !== ''">Nickname : {{ username }}</p>
          <p id="email" v-if="username !== ''">Email : {{ username }}@test.fr</p>
        </div>
      </div>
      <div class="footer">
        <p id="fiche">Fiche de {{ username === '' ? '???' : username }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ex_01.vue",
  data() {
    return {
      username: ''
    }
  }
}
</script>

<style scoped>
input {
  margin: 10px;
  border: 2px solid black;
}

.card {
  margin: 10px;
  width: 300px;
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.5);
  font-family: Courier, sans-serif;
}

.body {
  background: linear-gradient(45deg, rgb(255, 255, 255), rgb(96, 125, 139));
  padding: 5px;
  min-height: 150px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  border-bottom: 1px solid rgba(0,0,0,0.02);
}
.body>.info>p {
  margin: 10px 0;
}
.card > .footer {
  height: 30px;
  display: flex;
  align-items: center;
  margin: 0 5px;
}
</style>
