<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->

    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/week8">Week 8</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />

  <footer>
    <p>
      Author: Hege Refsnes<br />
      <a href="mailto:hege@example.com">hege@example.com</a>
    </p>
  </footer>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  background-color: cornflowerblue;
}

/* header {
  position: absolute;
  top: 0px;
  left: 0px;
  height: 200px;
  right: 0px;
  overflow: hidden;
} */

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  /* margin-top: 2rem; */
  padding: 5px;
}

nav a.router-link-exact-active {
  color: blue;
}

nav a.router-link-exact-active:hover {
  background-color: aqua;
}

nav a {
  /* display: inline-block; */
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  background-color: red;
  color: white;
  text-align: center;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
