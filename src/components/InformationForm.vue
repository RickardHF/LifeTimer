<template>
  <div class="information-form">
    <h2>Fill in you info</h2>
    <div class="information-row">
      <label for="nationality">Nationality</label>
      <select id="nationality" v-model="selectedCountry">
        <option :value="null">Select nationality</option>
        <option v-for="item in this.avgs" :key="item.name" :value="item">
          {{ item.name }}
        </option>
      </select>
    </div>
    <div class="information-row">
      <label>Date of Birth</label>
      <input type="date" v-model="dateOfBirth"/>
    </div>
    <div class="information-row">
      <label>Gender</label>
      <div class="information-cont-col">
        <div class="information-cont-row">
          <input type="radio" id="man" :value="true" v-model="man"/>
          <label for="man">Male</label>
        </div>
        <div class="information-cont-row">
          <input type="radio" id="woman" :value="false" v-model="man" title="Female"/>
          <label for="woman">Female</label>
        </div>
      </div>
    </div>
    <button :disabled="checkDisabled">Check</button>
    {{selectedCountry}}
  </div>
</template>

<script>

import { averageAges } from '../data/Ages'

export default {
  data() {
    return {
      avgs: averageAges,
      selectedCountry: null,
      dateOfBirth: null,
      man: null
    };
  },
  computed: {
    checkDisabled(){
      if(this.selectedCountry && this.dateOfBirth && this.man !== null) return false;
      return true;
    }
  }
};
</script>

<style>

h2 {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

select {
  text-align: center;
  padding: .1rem;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

input {
  padding: .1rem;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

option {
  display: flex;
  justify-content: center;
}

.information-form {
  background-color: var(--text-background);
  width: 80%;
  max-width: 700px;
  padding: 1.2rem;
  display: flex;
  justify-content: center;
  flex-direction: column;
  /*border: .2rem solid rgb(89, 84, 212);*/
  border-radius: .4rem;
  filter: drop-shadow(.2rem .2rem 1rem #000 )

}

.information-row label {
  width: 40%
}

.information-cont-col {
  display: flex;
  flex-direction: column;
}

.information-row {
  display: flex;
  justify-content: left;
  margin: 1rem;
}

.information-cont-row {
  display: flex;
  justify-content: left;
  margin: .3rem;
}

</style>
