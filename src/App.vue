<template>
  <div id="app" class="container is-fullhd" style="margin-top: 0;">
  <!-- the router outlet, where all matched components would ber viewed -->

  <section class="hero is-dark is-large">
    <!-- Hero header: will stick at the top -->
    <div class="hero-head">
      <header class="nav">
        <div class="container">
          <div class="nav-left">
            <a class="nav-item">
              <img src="static/logo.png" alt="Logo" style="max-height: 73px; padding-top: 14px;">
            </a>
          </div>
          <span class="nav-toggle">
            <span></span>
            <span></span>
            <span></span>
          </span>
          <div class="nav-right nav-menu">
            <a class="nav-item">
              <router-link v-bind:to="'/projects'">Проекты</router-link>
            </a>
            <a class="nav-item is-active">
              <router-link v-bind:to="'/sponsors'">Спонсоры</router-link>
            </a>
            <a class="nav-item is-active">
              <router-link v-bind:to="'/'"><i class="fa fa-user" aria-hidden="true"></i> Лиза,  <b>100 сот</b></router-link>
            </a>
            <!-- <a class="nav-item">
              Documentation
            </a>
            <span class="nav-item">
              <a class="button is-info is-inverted">
                <span class="icon">
                  <i class="fa fa-github"></i>
                </span>
                <span>Download</span>
              </a>
            </span> -->
          </div>
        </div>
      </header>
    </div>

  </section>

  <router-view></router-view>

<br>
  <footer class="footer">
    <div class="container">
      <div class="content has-text-centered">
        <p>
          <strong>Bulma</strong> by <a href="http://jgthms.com">Jeremy Thomas</a>. The source code is licensed
          <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content
          is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.
        </p>
        <p>
          <a class="icon" href="https://github.com/jgthms/bulma">
            <i class="fa fa-github"></i>
          </a>
        </p>
      </div>
    </div>
  </footer>

  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>
<!-- styling for the component -->
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
