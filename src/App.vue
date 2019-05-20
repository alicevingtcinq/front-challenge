<template>
  <div id="app">
    <h1>Exercice VueJS</h1>

    <div class="alert">
      <h2 class="title">Inputs</h2>
      <p>Etudier et comprendre le fonctionnement de l’input et du composant associé.</p>
    </div>

    <p class="separator"><span>App</span></p>
    <label for="test">Label : </label>
    <input class="input" v-model="model_4" name="test" id="test">
    <p>Choice : {{ model_4 }}</p>

    <p class="separator"><span>Component</span></p>
    <vq-input
    name="test"
    label="Label : "
    :model.sync="model_3"
    ></vq-input>

    <div class="alert">
      <h2 class="title">Radios</h2>
      <p>À partir de l'exemple des inputs, créér le composant pour radios.</p>
    </div>

    <p class="separator"><span>App</span></p>
    <input type="radio" id="one" value="One" v-model="model_1">
    <label for="one">One</label>
    <br>
    <input type="radio" id="two" value="Two" v-model="model_1">
    <label for="two">Two</label>
    <p>Choice : {{ model_1 }}</p>

    <p class="separator"><span>Component</span></p>
    <vq-radio></vq-radio>

    <div class="alert">
      <h2 class="title">Checkboxs</h2>
      <p>Créer le même système que dans les points précédents pour des checkboxs.</p>
    </div>

    <p class="separator"><span>App</span></p>
    <p><strong>TO DO</strong></p>

    <p class="separator"><span>Component</span></p>
    <p><strong>TO DO</strong></p>

    <div class="alert">
      <h2 class="title">Inté</h2>
      <p>Intégrer le bouton suivant en suivant les indications de la maquette sketch fournie.</p>
    </div>

    <div class="card">
      <button :disabled="isInputDisabled">{{ isInputDisabled | buttonLabel }}</button>
    </div>

  </div>
</template>

<script>

import vqRadio from '@/components/radio'
import vqInput from '@/components/input'

export default {
  name: 'app',
  components: { vqRadio, vqInput },
  filters: {
    buttonLabel(isDisabled) {
      if(isDisabled) {
        return 'Disabled'
      } else {
        return 'Valid'
      }
    }
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      model_1: 'One',
      model_2: 'One',
      model_3: 'test',
      model_4: 'test'
    }
  },
  computed: {
    isInputDisabled() {
      return this.model_3 != 'test' || this.model_4 != 'test'
    }
  }
}
</script>

<style lang="scss">
#app {
  padding: 20px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.alert {
  margin: 40px auto;
  padding: 10px;
  background: #eee;
  border-radius: 5px;
  border-top: 5px solid #aaa;
  counter-increment: card-counter;

  &:first-child {
    margin-top: 0;
  }

  .title {
    &:before {
      content: '- ' counter(card-counter) ' -';
      display: block;
      font-size: 14px;
    }
  }

  p {
    font-size: 14px;
  }
}

.separator {
  margin: 30px auto 10px;
  padding: 0;
  border-top: 1px solid #aaa;
  font-size: 12px;

  span {
    display: inline-block;
    padding: 5px 10px;
    transform: translateY(-50%);
    background: #aaa;
    color: #fff;
  }
}

h1, h2 {
  margin: 0 auto;
  font-weight: normal;
}

p {
  margin: 0 auto;
  padding: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

button {
  background-color: green;
  color: white;
}

button:disabled {
  background-color: red;
}
</style>
