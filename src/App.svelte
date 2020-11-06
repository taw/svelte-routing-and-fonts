<script>
  import Router from 'svelte-spa-router'
  import Home from './routes/Home.svelte'
  import About from './routes/About.svelte'
  import NotFound from './routes/NotFound.svelte'
  import Icon from './routes/Icon.svelte'

const routes = {
  '/': Home,
  '/about': About,
  '/icon/:name/:style?': Icon,
  '*': NotFound,
}
</script>

<style>
:global(header) {
  font-size: 400%;
}
nav {
  background-color: #ccc;
  margin-bottom: 10px;
  display: flex;
  gap: 10px;
}
</style>

<nav>
  <a href="#/">Home</a>
  <a href="#/about">About</a>
  <a href="#/icon/refresh/spin">Spin</a>
  <a href="#/icon/spinner/pulse">Pulse</a>
  <a href="#/icon/code">Code</a>
  <a href="#/fake-link">Fake Link</a>
</nav>

<Router {routes} />
