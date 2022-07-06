<template>
  <section class="highlighted-section" key="checkform">
    <h1 class="gradient-header">How long do I have to live?</h1>
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

.gradient-header {
    background: -webkit-linear-gradient(300deg, #ddd9d5 20%, #f8cfcf 70%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-box-decoration-break: clone;
}

.highlighted-section {
  padding-top: 2rem;
  padding-bottom: 2rem;
  justify-content: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #FFFFFF25;
}

</style>
