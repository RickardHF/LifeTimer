<template>
  <div class="information-form">
    <div class="form-result" v-if="expectedDeath">
      <div class="overlived" v-if="deathOverTime">
        <h3>Congratulations!</h3>
        <h4>You have already lived longer than the average in your country</h4>
        <h3>You have {{daysInExcess}}</h3>
        <div class="countdown-calender">
          <div class="calender-item">
            {{daysInExcess.years}}
            <p>Years</p>
          </div>
          <div class="calender-item">
            {{daysInExcess.days}}
            <p>Days</p>
          </div>
          <div class="calender-item">
            {{daysInExcess.hours}}
            <p>Hours</p>
          </div>
          <div class="calender-item">
            {{daysInExcess.minutes}}
            <p>Minutes</p>
          </div>
          <div class="calender-item">
            {{daysInExcess.seconds}}
            <p>Seconds</p>
          </div>
        </div>
      </div>
      <div class="time-to-go" v-else>
        <h1 class="gradient-header">
          Watch as your time is running out!
        </h1>
        <p>You will die at {{expectedDeath}}</p>
        <div class="countdown-calender">
          <h3>Remaining time:</h3>
          <div class="calender-item">
            {{daysToGo.years}}
            <p>Years</p>
          </div>
          <div class="calender-item">
            {{daysToGo.days}}
            <p>Days</p>
          </div>
          <div class="calender-item">
            {{daysToGo.hours}}
            <p>Hours</p>
          </div>
          <div class="calender-item">
            {{daysToGo.minutes}}
            <p>Minutes</p>
          </div>
          <div class="calender-item">
            {{daysToGo.seconds}}
            <p>Seconds</p>
          </div>
        </div>
      </div>
      <button :onclick="goback"> ⤺ Go Back</button>
    </div>
    <div class="form-filling" v-else>
      <h2 class="gradient-header">How long do I have to live?</h2>
      <p>Use our lifeexpectancy calculator to estimate how long you have left to live!</p>
      <br/>
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
            <label for="man">♂ Male</label>
          </div>
          <div class="information-cont-row">
            <input type="radio" id="woman" :value="false" v-model="man" title="Female"/>
            <label for="woman">♀ Female</label>
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

.countdown-calender {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  justify-content: center;
  background-color: var(--dark-color-lig);
  margin-top: 2rem;
  margin-bottom: 2rem;
  padding-top: 1rem;
  padding-bottom: 1rem;
  filter: drop-shadow(.3rem .3rem .6rem #000000a0)
}

.countdown-calender h3 {
  width: 100%;
  color: var(--text-background);
}

.calender-item {
  margin: .5rem;
  padding: .5rem;
  min-width: 4rem;
  font-size: 1.2rem;
  color: var(--dark-color);
  border-radius: .5rem;
  background-color: var(--text-background);
  display: flex;
  flex-direction: column;
  justify-items: center;
  align-items: center;
  filter: drop-shadow(.1rem .1rem .3rem #000000a0)
}

.calender-item p {
  font-size: .8rem;
  color: var(--dark-color-lig);
}

button {
  transition-duration: 0.4s;
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

select {
  text-align: center;
  padding: .1rem;
}

input {
  padding: .1rem;
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
  /*border: .2rem solid rgb(89, 84, 212);
  border-radius: .4rem;
  filter: drop-shadow(.2rem .2rem 1rem #000 )*/

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
