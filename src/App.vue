<template>
  <header>
    <div class="logo">
      <svg xmlns="http://www.w3.org/2000/svg" height="48" width="48">
        <path d="M15.8 41h16.4v-6.35q0-3.5-2.375-6.025Q27.45 26.1 24 26.1t-5.825 2.525Q15.8 31.15 15.8 34.65ZM8 44v-3h4.8v-6.35q0-3.5 1.825-6.425T19.7 24q-3.25-1.3-5.075-4.25Q12.8 16.8 12.8 13.3V7H8V4h32v3h-4.8v6.3q0 3.5-1.85 6.45T28.3 24q3.25 1.3 5.075 4.225Q35.2 31.15 35.2 34.65V41H40v3Z"/>
      </svg>
      <h3>
        How long will I live?
      </h3>
    </div>
    <NavBar/>
  </header>
  <section class="std-section" id="home">
    <h1>How long will I live?</h1>
    <p>
      Many of us spend time worrying how short life is, while others rather not think about it at all or think they'll live forever. Death is a difficult question for us humans, yet 
      it's something awaiting us all. While it is not good to ponder on ones own death at all times or to give one self to despair, it can also be bad 
      not to consider how valueable time is.
    </p>
    <figure>
      <blockquote class="citation">
        <h2>
          "Think of yourself as dead, you have lived your life. Now take what's left and live it properly"
        </h2>
      </blockquote>
      <cite>Marcus Aurelius</cite>
    </figure>
    <p>
      Our aim is here to give a usefull perspective on life. Seing how much or little is left of ones life in clear numbers can for many be a real eye opener.
    </p>
    <br/>
  </section>
  <section class="highlighted-section" key="checkform" id="calculator">
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
  <section class="lighter-section std-section" id="faq">
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
    </div>
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
    <br/>
    <br/>
  </section>
  <section class="std-section" id="inspqoutes">
    <h1>Inspirational Qoutes</h1>
    <figure>
      <blockquote class="citation">
        <h2>
          "He who fears death will never do anything worthy of a man who is alive."
        </h2>
      </blockquote>
      <cite>Seneca</cite>
    </figure>
    <figure>
      <blockquote class="citation">
        <h2>
          "In your actions, don't procrastinate. In your conversations, don't confuse. In your thoughts, don't wander. In your soul, don't be passive or aggressive. In your life, don't be all about business."
        </h2>
      </blockquote>
      <cite>Marcus Aurelius</cite>
    </figure>
    <figure>
      <blockquote class="citation">
        <h2>
          "This is our big mistake: to think we look forward to death. Most of death is already gone. Whatever time has passed is owned by death."
        </h2>
      </blockquote>
      <cite>Seneca</cite>
    </figure>
    <figure>
      <blockquote class="citation">
        <h2>
          "How long are you going to wait before you demand the best for yourself?"
        </h2>
      </blockquote>
      <cite>Epictetus</cite>
    </figure>
  </section>
  <footer>
    <h3>Pages</h3>
    <div class="page-links">
      <a href="/#home">
        Home
      </a>
      <a href="/#calculator">
        Calculate
      </a>
      <a href="/#faq">
        FAQ
      </a>
      <a href="/#inspqoutes">
        Inspirational Qoutes
      </a>
    </div>
    <br/>
    <br/>
    <div class="logo">
      <svg xmlns="http://www.w3.org/2000/svg" height="1.5rem" viewBox="0 0 48 48">
        <path d="M15.8 41h16.4v-6.35q0-3.5-2.375-6.025Q27.45 26.1 24 26.1t-5.825 2.525Q15.8 31.15 15.8 34.65ZM8 44v-3h4.8v-6.35q0-3.5 1.825-6.425T19.7 24q-3.25-1.3-5.075-4.25Q12.8 16.8 12.8 13.3V7H8V4h32v3h-4.8v6.3q0 3.5-1.85 6.45T28.3 24q3.25 1.3 5.075 4.225Q35.2 31.15 35.2 34.65V41H40v3Z"/>
      </svg>
      <h4>
        How long will I live?
      </h4>
    </div>
  </footer>
</template>

<script>
import InformationForm from './components/InformationForm.vue'
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    InformationForm,
    NavBar
}
}
</script>

<style>

.logo {
  display: flex;
  align-items: center;
  justify-content: center;
}

header {
  /*background: linear-gradient(180deg, var(--text-background) 85%, var(--dark-color-lig));*/
  background-color: var(--text-background);
  filter: drop-shadow(.3rem .3rem .6rem #000000a0);
  margin-bottom: 4rem;
  color: var(--dark-color);
  display: flex;
  padding-right: 3rem;
  padding-left: 3rem;
  justify-content: space-between;
  align-items: center;
}

.page-links {

}

.page-links a {
  margin: .5rem;
  font-weight: bolder;
  text-decoration: none;
  color: var(--dark-color);
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
  padding-top: 2rem;
  padding-bottom: 2rem;
  color: var(--dark-color);
}


</style>
