<template>
  <div id="app">
    <section class="hero is-info is-large has-bg-img">
      
      <div class="hero-head">
      <b-navbar
      :transparent="true"
      :spaced="true"
      >
        <template slot="brand">
            <b-navbar-item tag="router-link" :to="{ path: '/' }">
                <img
                    src="./assets/logo.png"
                    alt="Lightweight UI components for Vue.js based on Bulma"
                >
            </b-navbar-item>
        </template>
        <template slot="start">
            <b-navbar-item href="#">
                Home
            </b-navbar-item>
            <b-navbar-item href="https://ndocs.nextblu.com/">
                Documentation
            </b-navbar-item>
            <b-navbar-item>
                <b-taglist attached>
                    <b-tag type="is-dark">TentaLog</b-tag>
                    <b-tag type="is-info">{{tentalog_version}}</b-tag>
                </b-taglist>
            </b-navbar-item>
        </template>

        <template slot="end">
          <a class="button is-info is-inverted" href="https://github.com/nextblu/tentalog" target="_blank">
                <span class="icon">
                  <i class="fab fa-github"></i>
                </span>
                <span>Read the code</span>
              </a>
            <b-navbar-item tag="div">
                <div class="buttons">
                    <a class="button is-primary">
                        <strong>Sign up</strong>
                    </a>
                    <a class="button is-light">
                        Log in
                    </a>
                </div>
            </b-navbar-item>
        </template>
    </b-navbar>
      </div>

      <div class="hero-body">
        
      </div>

      <div class="hero-foot">
        <nav class="tabs is-boxed is-fullwidth">
          <div class="container">
            <ul>
              <li class="is-active">
                <a class="sub-menu-item">Overview</a>
              </li>
              <li>
                <a class="sub-menu-item-spaced">Example <b-tag :ellipsis="true">Soon</b-tag></a>
              </li>
              <li>
                <a class="sub-menu-item-spaced">The Web UI <b-tag>Soon</b-tag></a>
              </li>
            </ul>
          </div>
        </nav>
      </div>
    </section>


    <router-view/>


    <footer class="footer">
      <div class="content has-text-centered">
        <p>
          <strong>TentaLog</strong> by <a href="https://www.nextblu.com">NextBlu</a>. The source code is licensed
          <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content
          is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
const axios = require('axios').default;
export default {
  data() {
    return {
      tentalog_version: 'loading..'
    }
  },
  mounted() {
    console.log('Getting TentaLog version.')
    let vm = this;
    let github_api = "https://api.github.com/repos/nextblu/tentalog/tags";
    axios.get(github_api).then((response) => {
      console.log(response.data[0].name)
      vm.tentalog_version = response.data[0].name;
    })
  }
}
</script>

<style>
@import '../node_modules/typeface-roboto/index.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.has-bg-img { 
  /*background: url('https://images.unsplash.com/photo-1556075798-4825dfaaf498?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1510&q=80')center center; 
  */background: #4A90E2 url('./assets/tentalog-bg-01.png') center center; 
  background-size: contain;
  background-repeat: no-repeat;
  background-color: #4A90E2 !important;
}

.page-title {
  width: 50% !important;
  display: inline-block;
  background: gray;    
  transform: skewX(-10deg);
  border-radius: 2px;
  font-family: Roboto;
}

.sub-menu-item {
  color: #2c3e50 !important;
}

.sub-menu-item-spaced {
  justify-content: space-between;
}

</style>
