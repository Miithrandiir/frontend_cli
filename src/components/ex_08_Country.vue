<template>
  <div class="card w-100 card-country m-2">
    <div class="card-body">
      <div class="d-flex flex-row align-items-center">
        <BIconGlobe2 font-scale="5"/>
        <div class="d-flex flex-column flex-grow-1">
          <h3 class="fw-bold m-0 text-center">{{ country.name }}</h3>
          <p class="text-center">
            Calling Code : {{ country.callingCodes.join(', ') }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ex_08_Country",
  props: {
    country: Object
  }
}
</script>

<style scoped>
.card-country {
  max-width: 450px;
}
</style>
