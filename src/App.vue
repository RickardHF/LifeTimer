<template>
  <section class="highlighted-section" key="checkform">
    <InformationForm></InformationForm>
  </section>
</template>

<script>
import InformationForm from './components/InformationForm.vue'

export default {
  name: 'App',
  components: {
    InformationForm
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  justify-content: center;

}

.highlighted-section {
  padding-top: 2rem;
  padding-bottom: 2rem;
  justify-content: center;
  display: flex;
  background-color: #FFFFFF25;
}

</style>
