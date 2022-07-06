<template>
  <div class="information-form">
    <div class="form-result" v-if="expectedDeath">
      <div class="overlived" v-if="deathOverTime">
        <h3>Congratulations!</h3>
        <h4>You have already lived longer than the average in your country</h4>
        <h3>You have {{daysInExcess}}</h3>
      </div>
      <div class="time-to-go" v-else>
        <p>You will die at {{expectedDeath}}</p>
        <h3>You have {{daysToGo}}</h3>
      </div>
      <button :onclick="goback">Go Back</button>
    </div>
    <div class="form-filling" v-else>
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
      <button :disabled="checkDisabled" :onclick="calculateRemainingTime">How long do I have left?</button>
    </div>
    <br/>
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
      man: null,
      expectedDeath: null,
      now: Date.now(),
      timer: null
    };
  },
  computed: {
    checkDisabled(){
      if(this.selectedCountry && this.dateOfBirth && this.man !== null) return false;
      return true;
    },
    deathOverTime() {
      return this.expectedDeath < Date.now()
    },
    daysToGo(){
      let dist = this.expectedDeath - this.now
      
      var years = Math.floor(dist / (365 * 1000 * 60 * 60 * 24))
      let rem = dist % (365 * 1000 * 60 * 60 * 24);
      var days = Math.floor(rem / (1000 * 60 * 60 * 24));
      rem = rem % (1000 * 60 * 60 * 24);
      var hours = Math.floor(rem / (1000 * 60 * 60));
      rem = rem % (1000 * 60 * 60)
      var minutes = Math.floor(rem / (1000 * 60));
      rem = rem % (1000 * 60);
      var seconds = Math.floor((dist % (1000 * 60)) / 1000);

      return {
        years: years,
        days: days,
        hours: hours,
        minutes: minutes,
        seconds: seconds
      }
    },
    daysInExcess(){
      console.log(this.expectedDeath)
      let dist = this.now- this.expectedDeath
      
      var years = Math.floor(dist / (365 * 1000 * 60 * 60 * 24))
      let rem = dist % (365 * 1000 * 60 * 60 * 24);
      var days = Math.floor(rem / (1000 * 60 * 60 * 24));
      rem = rem % (1000 * 60 * 60 * 24);
      var hours = Math.floor(rem / (1000 * 60 * 60));
      rem = rem % (1000 * 60 * 60)
      var minutes = Math.floor(rem / (1000 * 60));
      rem = rem % (1000 * 60);
      var seconds = Math.floor((dist % (1000 * 60)) / 1000);

      return {
        years: years,
        days: days,
        hours: hours,
        minutes: minutes,
        seconds: seconds
      }
    }
  },
  methods: {
    calculateRemainingTime(){
      if(this.man){
        let dob = new Date(this.dateOfBirth);
        let manYears = this.selectedCountry.averageMen * 1000 * 60 * 60 *24 * 365;
        let d = new Date();
        d.setTime(manYears + dob.getTime())
        this.expectedDeath = d;
        console.log(this.expectedDeath)
      } else {
        let dob = new Date(this.dateOfBirth);
        let womanYears = this.selectedCountry.averageWomen * 1000 * 60 * 60 *24 * 365;
        let d = new Date();
        d.setTime(womanYears + dob.getTime())
        this.expectedDeath = d;
      }
    },
    goback(){
      this.expectedDeath = null
    }
  },
  created() {
    this.timer = setInterval(() => {this.now = Date.now()}, 1000)
  }
};
</script>

<style>

button {
  transition-duration: 0.4s;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  background-color: var(--dark-color);
  border-radius: 5px;
  padding: 5px;
  color: var(--text-background);
}

button:hover {
  background-color: var(--dark-color-lig);
  cursor: pointer;
}

button:disabled {
  background-color: var(--dark-color-dis);
  color: var(--text-color-dis);
}

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
