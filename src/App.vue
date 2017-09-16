<template>
  <div id="app" class="container is-fullhd">
  <!-- the router outlet, where all matched components would ber viewed -->

  <section class="hero is-info is-large">
    <!-- Hero header: will stick at the top -->
    <div class="hero-head">
      <header class="nav">
        <div class="container">
          <div class="nav-left">
            <a class="nav-item">
              <img src="images/bulma-type-white.png" alt="Logo">
            </a>
          </div>
          <span class="nav-toggle">
            <span></span>
            <span></span>
            <span></span>
          </span>
          <div class="nav-right nav-menu">
            <a class="nav-item is-active">
              <router-link v-bind:to="'/'">Home</router-link>
            </a>
            <a class="nav-item">
              <router-link v-bind:to="'/projects'">Projects</router-link>
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
