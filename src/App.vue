<template>
  <section class="std-section">
    <h1>How long will I live?</h1>
    <p>
      Many of us spend time worrying how short life is, while others rather not think about it at all or think they'll live forever. Death is a difficult question for us humans, yet 
      it's something awaiting us all. While it is not good to ponder on ones own death at all times or to give one self to despair, it can also be bad 
      not to consider how valueable time is.
    </p>
    <figure>
      <blockquote class="citation">
        <h2>
          "Think of your self as dead, you have lived your life. Now take what's left and live it properly"
        </h2>
      </blockquote>
      <cite>Marcus Aurelius</cite>
    </figure>
    <p>
      Our aim is here to give a usefull perspective on life. Seing how much or little is left of ones life in clear numbers can for many be a real eye opener.
    </p>
    <br/>
  </section>
  <section class="highlighted-section" key="checkform">
    <InformationForm></InformationForm>
  </section>
  <section class="std-section">
    <figure>
      <blockquote class="citation">
        <h2>
          "It is not death that a man should fear, but he should fear never beginning to live."
        </h2>
      </blockquote>
      <cite>Marcus Aurelius</cite>
    </figure>
  </section>
  <section class="lighter-section std-section">
    <h1>FAQ</h1>
    <div class="faq-container">
      <!--

        <details>
          <summary>How accurate is this prediction?</summary>
        <p>
          This prediction is only based on the life expectancy of your nationality for your gender. There are many other factors determinating how long you will
          live, such as health, genes, health habits, smoking, drinking etc.
        </p>
      </details>
      <details>
        <summary>I have only a few years left, what now?</summary>
        <p>
          This estimation is by no means a definitive answer to how long left you have to live, and is derrived only out of the life expectancy. Don't get too troubled with 
          the results. If you are worried about this, contact your doctor to get a better evaluation.
        </p>
      </details>
      <details>
        <summary>I have surpassed the life expectancy, what now?</summary>
        <p>
          Congratulations, you have lived longer than what is expected! Don't worry too much about the results, you might still have many more years left.
          If you are worried about this, contact your doctor to get a better evaluation.
        </p>
      </details>
      -->
      <p class="faq-header">How accurate is this prediction?</p>
      <p>
        This prediction is only based on the life expectancy of your nationality for your gender. There are many other factors determinating how long you will
        live, such as health, genes, health habits, smoking, drinking etc.
      </p>
      <p class="faq-header">I have only a few years left, what now?</p>
      <p>
        This estimation is by no means a definitive answer to how long left you have to live, and is derrived only out of the life expectancy. Don't get too troubled with 
        the results. If you are worried about this, contact your doctor to get a better evaluation.
      </p>
      <p class="faq-header">I have surpassed the life expectancy, what now?</p>
      <p>
        Congratulations, you have lived longer than what is expected! Don't worry too much about the results, you might still have many more years left.
        If you are worried about this, contact your doctor to get a better evaluation.
      </p>
    </div>
    <br/>
    <br/>
    <br/>
  </section>
  <footer>mh.</footer>
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

details {
  width: 100%;
  max-width: 650px;
  margin-top: 2rem;
}

details p {
  width: 100%;
}

details>summary { 
  list-style: none;
}
summary::after {
  content: ' ►';
}
details[open] summary:after {
  content: " ▼";
}

summary {
  font-size: larger;
  font-weight: bold;
}

.faq-header {
  font-size: larger;
  font-weight: bold;
}

.faq-header p {
  width: 100%;
}

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

p {
  width: 80%;
  max-width: 650px;
}

.citation {
  max-width: 400px;
}

figure {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h2, p, h3, h1, h4, input, button, select {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.gradient-header {
    background: -webkit-linear-gradient(300deg, var(--dark-color) 20%, #9c67ff 70%);
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
  background-color: #ffffff;
}

.lighter-section {
  background-color: #FFFFFF1D;
}

.std-section {
  color: var(--text-background);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: left;
  font-size: larger;
}

footer {
  background-color: var(--text-background);
}

</style>
