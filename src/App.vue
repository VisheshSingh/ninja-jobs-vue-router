<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/jobs">Jobs</router-link>
  </div>
  <router-view />
</template>

<style>
body {
  max-width: 720px;
  margin: 0 auto;
}
@media screen and (max-width: 720px) {
  body {
    max-width: 80%;
  }
}
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
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

#nav a.router-link-exact-active {
  background-color: crimson;
  color: #fff;
}
</style>
